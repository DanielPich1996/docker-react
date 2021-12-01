pipeline {
    agent { 
        label 'macos' 
    }
    stages {
        stage('check docker') {
            steps {
                sh '''
                    docker --version
                    docker-compose version
                '''
            }
        }
        stage('build') {
            steps {
                sh '''
                    - docker build -t danielpich/docker-react -f Dockerfile.dev .
                '''
            }
        }
        stage('test') {
            steps {
                sh '''
                    docker run -e CI=true danielpich/docker-react npm run test
                '''
            }
        }
    }
}

// pipeline {
//     agent any
//     stages {
//         stage('build') {
//             steps {
//                 sh ''' 
//                     docker build -t danielpich/docker-react  -v /var/run/docker.sock:/var/run/docker.sock -f Dockerfile.dev .
//                     ''' 
//             }
//         }
//         stage('test') {
//             steps {
//                 echo 'testing'
//             }
//         }
//         stage('deploy') {
//             steps {
//                 echo 'deploying'
//             }
//         }
//     }
// }