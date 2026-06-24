pipeline {
    agent any

    stages {

        stage('Create Artifact') {
            steps {
                sh 'echo "DevOps Training Day 46" > sample-artifact.txt'
            }
        }

        stage('Upload Artifact to Nexus') {
            steps {
                nexusArtifactUploader(
                    nexusVersion: 'nexus3',
                    protocol: 'http',
                    nexusUrl: '13.201.33.84:8081',
                    groupId: 'com.devops.training',
                    version: '2.0',
                    repository: 'maven-releases',
                    credentialsId: 'nexus-credentials',
                    artifacts: [[
                        artifactId: 'sample-app',
                        classifier: '',
                        file: 'sample-artifact.txt',
                        type: 'txt'
                    ]]
                )
            }
        }
    }
}
