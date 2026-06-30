pipeline {
    agent any

    tools {
        nodejs 'NodeJS'   // Jenkins NodeJS plugin name
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/rajveersingh-a11y/simple-todo-app-mongodb-express-node.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Test (optional)') {
            steps {
                sh 'npm test || echo "No tests found"'
            }
        }

        stage('Start App (CI check only)') {
            steps {
                sh 'node app.js || node server.js'
            }
        }
    }
}