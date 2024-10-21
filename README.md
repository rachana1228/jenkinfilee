pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/rachana1228/college.git', branch: 'main'
            }
        }
        stage('Build and Test') {
            parallel {
                stage('Build') {
                    steps {
                        echo 'Building the application...'
                        // Add your build commands
                    }
                }
                stage('Unit Tests') {
                    steps {
                        echo 'Running unit tests...'
                        // Add your unit test commands
                    }
                }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Add your deployment commands
            }
        }
    }
}
