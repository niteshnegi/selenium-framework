pipeline {
    agent any

    tools {
        jdk 'Java17'
        maven 'Maven-latest'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/niteshnegi/selenium-framework.git'
            }
        }

        stage('Build and Test') {
            steps {
                bat 'mvn clean test'
            }
        }
    }

    post {
        always {
            junit '**/surefire-reports/*.xml'
        }
    }
}
