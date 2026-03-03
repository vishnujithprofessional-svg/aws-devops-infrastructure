pipeline {
    agent any

    environment {
        AWS_REGION = "us-east-1"
        ECR_REPO = "app-448-repo"
        IMAGE_TAG = "latest"
        ACCOUNT_ID = "$(aws sts get-caller-identity --query Account --output text)"
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                credentialsId: 'github-448',
                url: 'https://github.com/vishnujithprofessional-svg/node-app-448.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t node-app-448 .'
            }
        }
    }
}
