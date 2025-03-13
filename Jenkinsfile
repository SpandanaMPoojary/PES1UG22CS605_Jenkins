pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[url: 'https://github.com/SpandanaMPoojary/PES1UG22CS605_Jenkins.git']]])
            }
        }
        
        stage('Build') {
            steps {
                build 'PES1UG22CS605-1'
                sh 'g++ ./main/wrong.cpp -o output'
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'this is the deployment stage'
            }
        }
    }

    post {
        failure {
            error 'Pipeline failed'
        }
    }
}

