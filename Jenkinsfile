stage('Run Container') {
    steps {
        sh '''
        docker rm -f flask-app || true
        docker run -d -p 5000:5000 --name flask-app flask-app
        '''
    }
}