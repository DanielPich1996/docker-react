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
                sh ''' 
                    docker build -t danielpich/docker-react  -v /var/run/docker.sock:/var/run/docker.sock -f Dockerfile.dev .
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