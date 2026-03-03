pipeline {
    agent any

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
                sh 'sudo docker build -t node-app-448 .'
            }
        }
    }
}
