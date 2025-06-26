pipeline {
    agent any

    environment {
        // Optional: reference your secret if needed (e.g., API key or token)
        MY_SECRET = credentials('1001')  // Replace with your actual Jenkins credential ID
    }

   

    }
 stages {
        stage('Checkout Code') {
            steps {
                git credentialsId: '1001', url: 'https://github.com/annahristova/vmbix.git'
            }
        }


    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}
    
