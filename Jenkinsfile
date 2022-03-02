#!/usr/bin/env groovy 
pipeline{
    agent any
    stages{
        stage("Test"){
            steps{
                echo "========Testing the application========"
            }
        }
        stage("Build"){
            steps{
                echo "========Building the applications========"
            }
        }
        stage("Deploy"){
            steps{
                script {
                    echo "========Deploy the applications========"
                    def dockerCmd = 'docker run -p 3000:3080 -d vijay815/demo-app:1.10'
                    sshagent(['ec2-server-key']) {
                        sh "ssh -o StrictHostKeyChecking=no ec2-user@18.206.186.93 ${dockerCmd}"
                    }

                }
                

            }
        }
    }

}