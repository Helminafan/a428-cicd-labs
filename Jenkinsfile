pipeline {
    agent {
        docker {
            image 'node:18.18.2-buster-slim'
            args '-p 3000:3000'
        }
    }
    stages {
        stage('Build') {
           
            steps {
                sh 'npm cache clean --f'
                sh 'npm install'
            }
        }
      
    }
}