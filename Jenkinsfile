pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout code from Git repository
                git url: 'https://github.com/jyothsna0411/Project-EM.git'
            }
        }
        stage('Build') {
            steps {
                // Build the Maven project
                sh 'mvn clean package'
            }
        }
        stage('Deploy') {
            steps {
                // Example: Deploy to a server or Docker registry
                sh 'echo "Deploying application"'
                // Add your deployment script here
            }
        }
    }
    
    post {
        success {
            echo 'Build successful! Application deployed.'
            // Add any post-build actions or notifications here
        }
        failure {
            echo 'Build failed :('
            // Add failure handling here if needed
        }
    }
}
