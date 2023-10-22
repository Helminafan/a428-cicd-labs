pipeline {
    agent {
        docker {
            image 'node:16-buster-slim' 
            args '-p 8081:8081' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install'
            }
        }
    }
}