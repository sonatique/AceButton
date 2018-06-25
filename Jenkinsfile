pipeline {
    agent { label 'master' }
    environment {
        AUNITER_ARDUINO_BINARY = '/var/lib/jenkins/arduino-1.8.5/arduino'
    }
    stages {
        stage('Setup') {
            steps {
                dir('AUniter') {
                    git url: 'https://github.com/bxparks/AUniter',
                        branch: 'develop'
                }
            }
        }

        stage('Build') { 
            steps {
                sh 'AUniter/auniter.sh --config AceButton/AUniterConfig --boards nano --verify AceButton/tests/AceButtonTest'
            }
        }
    }
}
