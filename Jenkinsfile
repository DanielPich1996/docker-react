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
    agent 
    {
        docker
        {
            image 'node:16-alpine'
            args '-u root -p 8081:8081 -v /var/run/docker.sock:/var/run/docker.sock  '
        }
    } 
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