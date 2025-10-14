pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo "📥 Cloning GitHub Repository..."
                git url: 'https://github.com/Mani0437/ATM--Console-Based.git', branch: 'main'
            }
        }

        stage('Setup Python') {
            steps {
                sh '''
                    echo "🐍 Checking Python version..."
                    python3 --version
                '''
            }
        }

        stage('Run ATM Program') {
            steps {
                sh '''
                    echo "▶️ Running ATM Python Program (auto input mode)..."
                    
                    # Run the Python file and provide '5' as input to exit gracefully
                    python3 "atm project.py" << EOF
5
EOF
                '''
            }
        }
    }

    post {
        success {
            echo '✅ ATM Project executed successfully in Jenkins pipeline!'
        }
        failure {
            echo '❌ Build failed. Please check the console output for errors.'
        }
    }
}
