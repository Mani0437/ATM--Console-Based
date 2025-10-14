pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Clone your GitHub repository
                git url: 'https://github.com/Mani0437/ATM--Console-Based.git', branch: 'main'
            }
        }

        stage('Setup Python') {
            steps {
                sh '''
                    echo "Checking Python version..."
                    python3 --version
                '''
            }
        }

        stage('Run ATM Program') {
            steps {
                sh '''
                    echo "Running ATM Python Program..."
                    python3 "atm project.py"
                '''
            }
        }
    }

    post {
        success {
            echo '✅ ATM Project executed successfully!'
        }
        failure {
            echo '❌ Build failed. Please check console logs.'
        }
    }
}
