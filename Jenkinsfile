pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'echo Building Application'
            }
        }

        stage('Test') {
            steps {
                sh 'echo Testing Application'
            }
        }

        stage('Deploy') {
            steps {
                sh 'cp index.html /tmp/index.html'
                sh 'echo Deployment Successful'
            }
        }

    }
}
