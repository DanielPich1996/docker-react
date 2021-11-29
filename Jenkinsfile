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
    agent any
    stages {
        stage('build') {
            steps {
                docker build -t danielpich/docker-react -f Dockerfile.dev . -v /var/run/docker.sock:/var/run/docker.sock 
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