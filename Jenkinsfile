pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo '📦 Fetching frontend + backend code from GitHub...'
                deleteDir()
                git branch: 'main', url: 'https://github.com/kaviya-sharon14/ssssssss.git'
            }
        }

        stage('Setup Python Environment') {
            steps {
                echo '🐍 Setting up Python & dependencies...'
                bat '''
                python -m venv venv
                call venv\\Scripts\\activate
                pip install --upgrade pip
                pip install flask
                '''
            }
        }

        stage('Run Flask App in Background') {
            steps {
                echo '🚀 Starting Flask app (backend + frontend combined)...'
                bat '''
                start /B venv\\Scripts\\python login.html
                '''
            }
        }

        stage('Access Link') {
            steps {
                echo '🔗 Your To-Do frontend is ready!'
                echo 'Open this link in your browser:'
                echo '👉 http://localhost:5000/'
            }
        }
    }

    post {
        failure {
            echo '❌ Pipeline failed. Please check the logs.'
        }
    }
}
