pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'g++ Jenkins-main/hello.cpp -o Jenkins-main/hello_exec'
            }
        }

        stage('Test') {
            steps {
                sh './Jenkins-main/hello_exec'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment Successful'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline Failed'
        }
    }
}
