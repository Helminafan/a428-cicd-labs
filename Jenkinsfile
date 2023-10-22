pipeline {
    agent {
        docker {
            image 'node:16-buster-slim' 
            args '-p 3011:3011' 
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