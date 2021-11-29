pipeline {
    agent {
        docker {
            image 'node:16-alpine'
            // Run the container on the node specified at the top-level of the Pipeline, in the same workspace, rather than on a new node entirely:
            reuseNode true
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t danielpich/docker-react -f Dockerfile.dev .'
            }
        }
    }
}