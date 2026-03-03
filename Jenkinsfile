pipeline {
    agent any

    environment {
        AWS_REGION = "us-east-1"
        ECR_REPO = "app-448-repo"
        IMAGE_TAG = "latest"
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

        stage('Push to ECR') {
            steps {
                script {
                    def ACCOUNT_ID = sh(script: "aws sts get-caller-identity --query Account --output text", returnStdout: true).trim()

                    sh """
                    aws ecr get-login-password --region ${AWS_REGION} | \
                    docker login --username AWS --password-stdin ${ACCOUNT_ID}.dkr.ecr.${AWS_REGION}.amazonaws.com

                    docker tag node-app-448:latest ${ACCOUNT_ID}.dkr.ecr.${AWS_REGION}.amazonaws.com/${ECR_REPO}:${IMAGE_TAG}

                    docker push ${ACCOUNT_ID}.dkr.ecr.${AWS_REGION}.amazonaws.com/${ECR_REPO}:${IMAGE_TAG}
                    """
                }
            }
        }
    }
}
