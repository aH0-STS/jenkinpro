pipeline {
    agent any // Runs on any available Jenkins agent

    stages {
        stage('Clone Repository') {
            steps {
                git url: 'https://github.com/aH0-STS/jenkinpro.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                // Deployment logic can be added here
            }
        }
    }

    post {
        success {
            echo '✅ Build and Test Successful!'
        }
        failure {
            echo '❌ Build Failed! Check logs.'
        }
    }
}
