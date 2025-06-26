pipeline {
    agent any

    environment {
        // Optional: reference your secret if needed (e.g., API key or token)
        MY_SECRET = credentials('my-secret-id')  // Replace with your actual Jenkins credential ID
    }

    stages {
        stage('Checkout Code') {
            steps {
                git credentialsId: 'my-git-creds-id', url: 'https://github.com/your-user/your-repo.git'
            }
        }

    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}
}   
