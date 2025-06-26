pipeline {
    agent any

    environment {
        // Optional: reference your secret if needed (e.g., API key or token)
        MY_SECRET = credentials('1001')  // Replace with your actual Jenkins credential ID
    }

   
agent {
        docker {
            image 'python:3.11'  // Or any Python version you need
            args '-u root'       // Use root if pip installs are needed
        }
    }
 stages {
        stage('Checkout Code') {
            steps {
                git credentialsId: '1001', url: 'https://github.com/annahristova/vmbix.git'
            }
        }
    stages {
        stage('Install Dependencies') {
            steps {
                sh 'python -m venv venv'
                sh '. venv/bin/activate && pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh '. venv/bin/activate && pytest tests/'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}
    
