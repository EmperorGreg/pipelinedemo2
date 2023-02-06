pipeline {
    agent any
    parameters {
        booleanParam(name: 'Refresh',
                    defaultValue: false,
                    description: 'Read Jenkinsfile and exit.')
            }
    stages {
        stage('update apt cache') {
            steps {
                sh 'sudo apt update'
            }
        }
        stage('install nginx') {
            steps {
                sh 'sudo apt install nginx -y'
            }
        }
        stage('connect via ssh') {
            steps {
                sh '''
                    #!/bin/bash
                    ssh -i /home/jenkins/.ssh/key -o StrictHostKeyChecking=no ubuntu@13.42.104.143 << EOF
                    touch /home/ubuntu/readme.md
                    echo "# Hello" > /home/ubuntu/readme.md
                    << EOF
                '''
            }
        }
    }
}