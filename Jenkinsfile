pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    // Clean npm cache to avoid corrupted files
                    sh 'npm cache clean --force'
                    // Install dependencies (use npm ci if using lock files)
                    sh 'npm install'  // or 'npm ci' if you have package-lock.json
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    // Run the build
                    sh 'npm run build'
                }
            }
        }
    }
}
