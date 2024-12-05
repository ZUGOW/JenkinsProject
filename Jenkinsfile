pipeline {
    agent any
    
    environment {
        // Optional: Define the GitHub repository URL and email
        REPO_URL = 'https://github.com/ZUGOW/JenkinsProject.git'
        EMAIL = 'gowthamaws8@gmail.com'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from the GitHub repository
                git url: "${REPO_URL}"
            }
        }

        stage('Build') {
            steps {
                // Add build commands (e.g., Maven, Gradle, etc.)
                sh 'echo "Building project..."'
            }
        }

        stage('Test') {
            steps {
                // Add test commands (e.g., running unit tests)
                sh 'echo "Running tests..."'
            }
        }

        stage('Notify') {
            steps {
                // Send an email notification after the build completes
                mail to: "${EMAIL}",
                     subject: "Jenkins Build: ${currentBuild.currentResult}",
                     body: "The build has completed successfully or failed.\n\nBuild Result: ${currentBuild.currentResult}"
            }
        }
    }

    post {
        always {
            // Clean up, if necessary
            echo 'Build completed, sending notification...'
        }
    }
}

