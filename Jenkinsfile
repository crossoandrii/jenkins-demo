pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'git@github.com:crossoandrii/jenkins-demo.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution completed.'
        }
        success {
            mail to: 'crossoandrey@gmail.com',
                 subject: "SUCCESSFUL BUILD: Job '${env.JOB_NAME}' [Build #${env.BUILD_NUMBER}]",
                 body: "The build executed successfully. Check the details at ${env.BUILD_URL}"
        }
        failure {
            mail to: 'crossoandrey@gmail.com',
                 subject: "FAILED BUILD: Job '${env.JOB_NAME}' [Build #${env.BUILD_NUMBER}]",
                 body: "The build failed! Please check the console output at ${env.BUILD_URL}"
        }
    }
}