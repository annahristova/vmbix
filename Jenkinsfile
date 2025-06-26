pipeline {
    agent any

    environment {
        // Optional: reference your secret if needed (e.g., API key or token)
        MY_SECRET = credentials('1001')  // Replace with your actual Jenkins credential ID
    }

    stages {
        stage('Checkout Code') {
            steps {
                git credentialsId: 'my-git-creds-id', url: 'https://github.com/annahristova/vmbix.git'
            }
        }
    }
    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}

