// pipeline {
//     agent { 
//         dockerfile true 
//     }
//     stages {
//         stage('Test') {
//             steps {
//                 sh 'node --version'
//             }
//         }
//     }
// }

pipeline {
    tool {
        docker 'docker'
    }
    agent any
    stages {
        stage('build') {
            steps {
                sh ''' 
                    docker build -t danielpich/docker-react -f Dockerfile.dev .
                    ''' 
            }
        }
        stage('test') {
            steps {
                echo 'testing'
            }
        }
        stage('deploy') {
            steps {
                echo 'deploying'
            }
        }
    }
}