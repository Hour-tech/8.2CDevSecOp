pipeline {
    agent any

    // Use the NodeJS tool installed via Global Tool Configuration
    tools {
        nodejs 'NodeJS 18' // Replace with the exact name you gave in Jenkins NodeJS configuration
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout your GitHub repository
                git branch: 'main', url: 'https://github.com/Hour-tech/8.2CDevSecOp.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                // Install all npm dependencies
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                // Run tests; continue even if tests fail
                sh 'npm test || true'
            }
        }

        stage('Generate Coverage Report') {
            steps {
                // Generate coverage report; continue even if it fails
                sh 'npm run coverage || true'
            }
        }

        stage('NPM Audit (Security Scan)') {
            steps {
                // Run security audit for npm packages; continue even if vulnerabilities exist
                sh 'npm audit || true'
            }
        }
        stage('SonarCloud Analysis') {
            steps {
                sh '''
                //your scripts
                '''
            }
    }

    post {
        always {
            // Print environment info for debugging
            sh 'node -v'
            sh 'npm -v'
        }
    }
}
