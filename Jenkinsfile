pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                sh 'mvn install'
            }
        }
        stage('docker build') {
            steps {
                sh 'docker build -t gitesh8/giteshproject2 .'
            }
        }
        stage('Container creation') {
            steps {
                sh 'docker run -it -d --name=giteshproject2 -p 8081:8080 gitesh8/giteshproject2 /bin/bash'
            }
        }
    }
}
