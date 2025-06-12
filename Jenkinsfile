pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git credentialsId: 'jenkins-ssh', url: 'git@github.com:Zumel-bot/node-app.git' // Замените на свой URL и ID учетных данных
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install -DskipTests=true' // Команда сборки Maven, пропускаем тесты на этапе сборки для скорости. Замените на свою команду.
            }
        }

        stage('Run') {
            steps {
                sh 'java -jar target/*.jar' // Запускаем собранный jar файл. Замените на свой путь и команду.
            }
        }
    }
}
