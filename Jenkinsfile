pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                git(branch: 'main', url: 'https://github.com/mariomerco/sample-docker-app.git')
            }
        }
        
        stage('Docker Build') {
            steps {
                sh "docker build --no-cache -t sample-app:v${BUILD_NUMBER} ."
            }
        }
        
        stage('Clean') {
            steps {
                sh "rm -r ./*"
            }
        }

        stage('Deployment') {
            steps {
                echo 'Im deploying to the Environment ${ENVIRONMENT}'
            }
        }
    }
}
