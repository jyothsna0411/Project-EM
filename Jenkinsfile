pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/jyothsna0411/Project-EM.git'
            }
        }
        stage('Build Image') {
            steps {
                script {
                    sh 'docker build -t jp0411/myapp .'
                }
            }
        }
        stage('Run') {
            steps {
                script {
                    // Stop and remove any existing container
                    sh 'docker stop myapp || true && docker rm myapp || true'
                    
                    // Run the new container
                    sh 'docker run -d --name myapp -p 8081:8081 jp0411/myapp'
                }
            }
        }
    }
    
    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build or deployment failed.'
        }
    }
}
