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
                sh 'g++ main/hello2.cpp -o main/output' // chnage the file name hello.cpp to helo.cpp 
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
