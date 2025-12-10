pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code from GitHub...'
                checkout scm
            }
        }
        stage('Install Dependencies') {
            steps {
                echo 'Installing Node.js dependencies...'
                bat 'node -v'      // check Node.js version
                bat 'npm -v'       // check npm version
                bat 'npm install'
            }
        }
        stage('Run Tests') {
            steps {
                echo 'Running tests...'
                bat 'npm test'
            }
        }
    }
    post {
        success {
            echo 'Build succeeded!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
