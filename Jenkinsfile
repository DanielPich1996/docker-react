pipeline {
    agent { 
        lable 'macos' 
    }
    stages {
        stage('Test') {
            steps {
                sh 'docker --version'
            }
        }
    }
}

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