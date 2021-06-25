pipeline {
    agent any
    environment {
      DOCKER_TAG = getVersion()
    }

    stages {
        stage('Stage Build With Docker image') {
            steps {
                sh 'docker build . -t happyit/myweb:${DOCKER_TAG}'
            }
        }


    }
}

def getVersion(){
    def commitHash = sh label: '', returnStdout: true, script: 'git rev-parse --short HEAD'
    return commitHash
}