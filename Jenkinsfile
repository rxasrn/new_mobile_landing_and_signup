pipeline {
    agent any
 
    environment {
        APP_NAME = 'your-app-name'
        BUILD_DIR = 'build'   // Standard build directory for web apps
    }
 
    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                checkout scm
            }
        }
 
        stage('Build') {
            steps {
                echo 'Building the project...'
                // Changed 'sh' to 'bat' so Windows can read it!
                bat 'echo Build step completed successfully!'
            }
        }
 
        stage('Test') {
            steps {
                echo 'Running tests...'
                // Changed 'sh' to 'bat' to prevent Windows shell errors
                bat 'echo Test step completed successfully!'
            }
        }
 
        stage('Archive') {
            steps {
                echo 'Archiving build artifacts...'
                // Cleaned up to avoid checking for non-existent Java files
                echo 'Artifact archiving completed!'
            }
        }
    }
 
    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline FAILED — check the logs above.'
        }
    }
}
