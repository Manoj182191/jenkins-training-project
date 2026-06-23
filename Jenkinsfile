pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Manoj182191/jenkins-training-project.git'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarServer') {
                    sh '''
                    /var/jenkins_home/tools/hudson.plugins.sonar.SonarRunnerInstallation/SonarScanner/bin/sonar-scanner \
                    -Dsonar.projectKey=devops-training-app \
                    -Dsonar.sources=. \
                    -Dsonar.host.url=http://13.126.187.64:9000
                    '''
                }
            }
        }
    }
}
