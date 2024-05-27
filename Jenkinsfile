pipeline {
    agent any

    environment {
        VERCEL_TOKEN = credentials('vercel-token') // Add your Vercel token to Jenkins credentials
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/ProductSingh/my-static-app.git', branch: 'master'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install -g vercel'
            }
        }

        stage('Deploy to Vercel') {
            steps {
                sh 'vercel --token $VERCEL_TOKEN --prod'
            }
        }
    }
}

