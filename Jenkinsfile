pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/your_github_username/8.2CDevSecOps.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                nodejs('NodeJS 18') {  
                    sh 'npm install'
                }
            }
        }

        stage('Run Tests') {
            steps {
                nodejs('NodeJS 18') {
                    sh 'npm test || true'
                }
            }
        }

        stage('Generate Coverage Report') {
            steps {
                nodejs('NodeJS 18') {
                    sh 'npm run coverage || true'
                }
            }
        }

        stage('NPM Audit (Security Scan)') {
            steps {
                nodejs('NodeJS 18') {
                    sh 'npm audit || true'
                }
            }
        }
    }
}
