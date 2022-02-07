pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                git(branch: 'main', url: 'https://github.com/mariomerco/sample-docker-app.git')
                sh("ls")
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
    }
}
