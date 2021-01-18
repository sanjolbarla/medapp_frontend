pipeline{
    agent any
    stages {
        stage('Build'){
            steps {
                bat 'npm install'
                bat 'type nul > .env'
                bat 'echo REACT_APP_SECRET_CODE=medApp> .env'
                bat 'npm run build'
            }
        }
        stage('Docker Build and Deploy'){
            steps {
                bat 'docker pull httpd'
                bat 'docker build -t medApp .'
                bat 'docker run -dit --name my-running-app -p 8081:80 medApp'
            }
        }
    }
}