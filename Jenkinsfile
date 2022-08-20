pipeline {
    agent any 
    stages {
        stage('update') {
            steps {
                sh 'sudo apt update '
            }
        }
        stage('build') {
            steps {
                sh 'sudo docker build . -t img '
                sh 'sudo docker rm -f auto '
            }
        }
        stage('run') {
            steps {
                sh 'sudo docker run -d -p 8000:8000 --name auto img '
            }
        }
    }
}
