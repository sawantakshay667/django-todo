pipeline {
    agent any 
    stages {
        stage('update') {
            steps {
                sh 'apt update '
                echo 
            }
        }
        stage('build') {
            steps {
                sh 'docker build . -t img'
                sh 'docker rm $(docker ps -a -q)'
            }
        }
        stage('run') {
            steps {
                sh 'docker run -d --name auto img'
            }
        }
    }
}
