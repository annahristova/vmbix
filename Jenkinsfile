pipeline {
    agent any

    environment {
        // Optional: reference your secret if needed (e.g., API key or token)
        MY_SECRET = credentials('1001')  // Replace with your actual Jenkins credential ID
    }

    stages {
        stage('Checkout Code') {
            steps {
                git credentialsId: '1001', url: 'https://github.com/annahristova/vmbix.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing Python dependencies...'
                sh 'python3 -m venv venv'
                sh '. venv/bin/activate && pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running pytest...'
                sh '. venv/bin/activate && pytest tests/'
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline completed successfully.'
        }
        failure {
            echo '❌ Pipeline failed. Check the logs.'
        }
    }
}
