pipeline {
    agent {
        docker {
            image 'node:14'
        }
    }
    stages {
        stage('Clone repository') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/rishireddy26/PES2UG22CS448_Jenkins.git'
            }
        }
        stage('Install dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Build application') {
            steps {
                sh 'npm run build'
            }
        }
        stage('Test application') {
            steps {
                sh 'npm test'
            }
        }
        stage('Push Docker image') {
            steps {
                sh 'docker build -t rishireddy26/myimage:$BUILD_NUMBER .'
                sh 'docker push rishireddy26/myimage:$BUILD_NUMBER'
            }
        }
    }
    post {
        failure {
            echo 'Pipeline Failed'
        }
    }
}
