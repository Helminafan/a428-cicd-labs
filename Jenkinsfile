pipeline {
    agent {
        docker {
            image 'node:18-buster-slim' 
            args '-p 5000:5000' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'node -v'
            }
        }
        //  stage('Test') { 
        //     steps {
        //         sh './jenkins/scripts/test.sh' 
        //     }
        // }

    }
    
}