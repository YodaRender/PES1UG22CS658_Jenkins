pipeline {
    agent any

    stages {
        // Build Stage
        stage('Build') {
            steps {
                script {
                    echo 'Building the C++ file...'
                    sh '''
                        # Compile the .cpp file
                        g++ -o PES1UG22CS658 PES1UG22CS658.cpp
                        echo 'Build completed: PES1UG22CS658 executable created.'
                    '''
                }
            }
        }

        // Test Stage
        stage('Test') {
            steps {
                script {
                    echo 'Testing the C++ file...'
                    sh '''
                        # Run the compiled executable and print output
                        ./PES1UG22CS658
                    '''
                }
            }
        }

        // Deploy Stage
        stage('Deploy') {
            steps {
                script {
                    echo 'Deploying the application...'
                    // Add deployment logic here (e.g., copying files to a server)
                    echo 'Deployment completed.'
                }
            }
        }
    }

    // Post-condition to handle pipeline failure
    post {
        failure {
            echo 'Pipeline failed!'
        }
        success {
            echo 'Pipeline succeeded!'
        }
    }
}
