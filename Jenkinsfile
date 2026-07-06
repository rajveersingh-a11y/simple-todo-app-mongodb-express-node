pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master',
                    url: 'https://github.com/rajveersingh-a11y/simple-todo-app-mongodb-express-node.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t todo-app:latest .'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl rollout restart deployment/todo-app'
            }
        }
    }
}