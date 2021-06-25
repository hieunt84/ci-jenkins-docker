pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                sh 'docker build . -t happyit/myweb:v1'
            }
        }
    }
}

def getVersion(){
    def commitHash = sh label: '', returnStdout: true, script: 'git rev-parse --short HEAD'
    return commitHash
}