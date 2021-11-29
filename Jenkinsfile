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
                echo 'building'
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