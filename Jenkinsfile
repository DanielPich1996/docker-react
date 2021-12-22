pipeline {
    agent { 
        label 'macos' 
    }
    environment {
        DOCKER_HUB_CREDS = credentials('danielpich-docker-hub')
        AWS_CREDS = credentials('danielpich-aws-cred')
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
        // stage('build') {
        //     steps {
        //         sh '''
        //             docker build -t danielpich/docker-react -f Dockerfile.dev .
        //         '''
        //     }
        // }
        // stage('test') {
        //     steps {
        //         sh '''
        //             docker run -e CI=true danielpich/docker-react npm run test
        //         '''
        //     }
        // }
        // stage('Deploy') {
        //     steps {
        //         sh '''
        //             docker context create ecs myecscontext --from-env
        //         '''
        //     }
        // }
        stage('Build') {
            steps {
                sh 'docker context use default'
                sh 'docker compose build'
                sh 'echo $DOCKER_HUB_CREDS_PSW | docker login -u $DOCKER_HUB_CREDS_USR --password-stdin'
                sh 'docker compose push'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker context create ecs myecscontext --from-env'
                sh 'docker context use myecscontext'
                sh 'docker compose up'
                sh 'docker compose ps --format json'
                sh 'docker context rm myecscontext'
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