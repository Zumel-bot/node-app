pipeline {
    agent any // Используем любой доступный агент Jenkins

    stages {
        stage('Checkout') {
            steps {
                git credentialsId: 'jenkins-ssh', url: 'git@github.com:Zumel-bot/node-app.git' // Замените на свой URL и ID учетных данных
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install' // Команда сборки Maven. Замените на свою команду.
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test' // Команда для запуска тестов. Замените на свою команду.
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...' // Замените на шаги развертывания
            }
        }
    }

    post {
        success {
            echo 'Build succeeded!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
