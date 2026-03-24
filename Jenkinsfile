pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Aditya09977/devops-final', branch: 'main'
            }
        }

        stage('Setup Environment') {
            steps {
                bat 'mvn clean install -DskipTests'
            }
        }

        stage('Run Selenium Tests') {
            steps {
                bat 'mvn test'
            }
        }
    }

    post {
        always {
            junit 'target/surefire-reports/*.xml'
        }
    }
}
