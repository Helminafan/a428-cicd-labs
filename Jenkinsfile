pipeline {
    agent {
        docker {
            image 'node:18.16.0-buster-slim'
            args '-p 4000:4000'
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