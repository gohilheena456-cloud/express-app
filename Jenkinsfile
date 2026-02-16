pipeline {
    agent any

    environment {
        APP_DIR = "/home/ubuntu/express-app"
    }

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/gohilheena456-cloud/express-app.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Restart Application') {
            steps {
                sh '''
                pm2 restart express-app || pm2 start app.js --name express-app
                '''
            }
        }
    }
}

