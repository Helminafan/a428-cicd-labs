pipeline {
    agent {
        docker {
            image 'node:16-buster-slim'
            args '-p 3000:3000'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') { 
            steps {
                sh './jenkins/scripts/test.sh' 
            }
        }
         stage('Manual Approval') {
            steps {
                 input(id: 'manual-approval', message: 'Lanjutkan ke tahap Deploy?', parameters: [booleanParam(name: 'PROCEED', description: 'Proceed?')], submitter: 'user')
            }
        }
        stage('Deploy') {
            steps {
                def approval = input(id: 'manual-approval')
                if (approval.PROCEED) {
                        echo 'Melanjutkan ke tahap Deploy...'
                        sleep time: 60, unit: 'SECONDS'
                        sh './jenkins/scripts/deploy.sh'
                    }
                else {
                     sh './jenkins/scripts/kill.sh'
                }
            }
        }
    }
}