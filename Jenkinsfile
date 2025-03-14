// Errorless code
pipeline {
    agent any

    stages {
        // Clone Repository Stage
        stage('Clone repository') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/YodaRender/PES1UG22CS658_Jenkins.git'
            }
        }

        // Build Stage
        stage('Build application') {
            steps {
                sh '''
                    cd main
                    g++ -o PES1UG22CS658-1 PES1UG22CS658.cpp
                '''
            }
        }

        // Test Stage
        stage('Test application') {
            steps {
                sh '''
                    cd main
                    ./PES1UG22CS658-1
                '''
            }
        }

        // Deploy Stage
        stage('Deploy application') {
            steps {
                echo 'Deploying application...'
            }
        }
    }

    // Post-Conditions
    post {
        failure {
            echo 'Pipeline failed!'
        }
        success {
            echo 'Pipeline executed successfully!'
        }
    }
}
// // Buggy code
// pipeline {
//     agent any

//     stages {
//         // Clone Repository Stage
//         stage('Clone repository') {
//             steps {
//                 git branch: 'main',
//                     url: 'https://github.com/YodaRender/PES1UG22CS658_Jenkins.git'
//             }
//         }

//         // Build Stage (Intentional Error)
//         stage('Build application') {
//             steps {
//                 sh '''
//                     cd main
//                     g++ -o PES1UG22CS658-1 non_existent_file.cpp  # Intentional error: file does not exist
//                 '''
//             }
//         }

//         // Test Stage
//         stage('Test application') {
//             steps {
//                 sh '''
//                     cd main
//                     ./PES1UG22CS658-1
//                 '''
//             }
//         }

//         // Deploy Stage
//         stage('Deploy application') {
//             steps {
//                 echo 'Deploying application...'
//             }
//         }
//     }

//     // Post-Conditions
//     post {
//         failure {
//             echo 'Pipeline failed!'  // This should execute if any stage fails
//         }
//         success {
//             echo 'Pipeline executed successfully!'
//         }
//     }
// }
