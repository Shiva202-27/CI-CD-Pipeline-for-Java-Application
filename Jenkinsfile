pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Shiva202-27/aws-devops-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t aws-devops-app .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh '''
                docker stop aws-app || true
                docker rm aws-app || true
                docker run -d -p 8082:80 --name aws-app aws-devops-app
                '''
            }
        }

    }
}
