pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/mariomerco/sample-docker-app.git'
            }
        }
        
        stage('Build docker image') {
            steps {
                sh "docker build -t simple-app:${BUILD_NUMBER} ."
            }
        }
        
        stage('Clear') {
            steps {
                sh "rm -r ./*"
            }
        }
    } 
}