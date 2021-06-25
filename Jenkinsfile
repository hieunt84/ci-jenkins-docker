pipeline {
    agent any
        stage('Stage Build With Docker image') {
            steps {         
                sh "docker build . -t happyit/myweb:1"
            }
        }     
                    
    }
}