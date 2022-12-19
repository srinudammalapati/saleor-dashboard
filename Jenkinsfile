pipeline {
    agent {label 'jdk11'}
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage ('git clone') {
            steps {
                git url: 'https://github.com/srinudammalapati/saleor-platform.git',
                branch: 'main'
            }

        }
         stage ('docker image build') {
            steps {
               sh 'docker image build -t sdb:1.0 .'
               sh 'docker image tag sdb:1.0 8688735853/sdb:1.0 '
            }

        }

    }
}