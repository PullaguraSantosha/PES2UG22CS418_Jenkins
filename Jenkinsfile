pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', 
                    branches: [[name: '*/main']], 
                    userRemoteConfigs: [[url: 'https://github.com/PullaguraSantosha/PES2UG22CS418_Jenkins.git']]
                ])
            }
        }

        stage('Build') {
            steps {
                sh 'g++ main/hello.cpp -o main/output' // change the file name hello2.cpp to helo2.cpp for error
            }
        }

        stage('Test') {
            steps {
                sh './main/output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }

    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
