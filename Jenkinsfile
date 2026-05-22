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
                bat 'echo Build step completed successfully!'
            }
        }
 
        stage('Test') {
            steps {
                echo 'Running tests...'
                bat 'echo Test step completed successfully!'
            }
        }
 
        stage('Archive') {
            steps {
                echo 'Archiving build artifacts...'
                echo 'Artifact archiving completed!'
            }
        }

        // Fixed: Moved the Deploy stage INSIDE the main stages block
        stage('Deploy') {
            steps {
                echo 'Deploying to server...'
                bat 'echo Deploying web app files successfully!'
            }
        }
    }
 
    // Fixed: Combined your console messages and emails into one master post block
    post {
        success {
            echo 'Pipeline completed successfully!'
            mail to: 'your-email@example.com',
                 subject: "BUILD SUCCESS: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                 body: "Good news! Build ${env.BUILD_URL} completed successfully."
        }
        failure {
            echo 'Pipeline FAILED — check the logs above.'
            mail to: 'your-email@example.com',
                 subject: "BUILD FAILED: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                 body: "Build ${env.BUILD_URL} has failed. Please check the logs."
        }
    }
}
