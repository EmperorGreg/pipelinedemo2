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
    }
}