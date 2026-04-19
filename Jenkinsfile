pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/GobirajM2003/flask-jenkins-docker-ci-cd-pipeline.git'
            }
        }

        stage('Check Docker') {
            steps {
                sh 'docker --version'
            }
        }

        stage('Build Image') {
            steps {
                sh 'docker build -t flask-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                    docker rm -f flask-app || true
                    docker run -d -p 5000:5000 --name flask-app flask-app
                '''
            }
        }
    }
}