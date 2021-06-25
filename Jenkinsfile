pipeline {
    agent any
    environment {
      DOCKER_TAG = getVersion()
    }
    stages {
        stage('Checkout Source') {
            steps {
                git 'https://github.com/hieunt84/ci-jenkins-docker.git'
        }
    }
        stage('Stage Build With Docker image') {
            steps {         
                docker build . -t happyit/myweb:${DOCKER_TAG}
            }
        }

        stage('Stage Docker Hub Push') {
            steps { 
                //withCredentials([string(credentialsId: 'docker_hub', variable: 'DockerHubPwd')]) {
                //    sh "docker login -u happyit -p ${DockerHubPwd}"
                //}               
                
                sh "docker login -u happyit -p Chualanh@2021"
                sh "docker push happyit/web2:${DOCKER_TAG}"
            }
        }
                    
    }
}

def getVersion(){
    def commitHash = sh label: '', returnStdout: true, script: 'git rev-parse --short HEAD'
    return commitHash
}