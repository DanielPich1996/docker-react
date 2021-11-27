pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                docker build -t danielpich/docker-react -f Dockerfile.dev .
            }
        }
    }
}