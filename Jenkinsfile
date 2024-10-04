pipeline {
    agent any

    environment {
        GIT_REPO = 'https://github.com/gskhadka/website.git'
        DEPLOY_DIR = '/var/www/html' // Change this to your web server directory
    }

    stages {
        stage('Clone Repository') {
            steps {
                // Clone the repository
                git branch: 'main', url: "${GIT_REPO}"
            }
        }

        stage('Build') {
            steps {
                script {
                    // List files for verification (optional)
                    sh 'ls -al'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Copy index.html to the deployment directory
                    sh "sudo cp index.html ${DEPLOY_DIR}/"
                }
            }
        }
    }

    post {
        success {
            echo 'Deployment successful!'
        }
        failure {
            echo 'Deployment failed.'
        }
    }
}
