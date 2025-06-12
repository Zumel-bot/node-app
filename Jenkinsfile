pipeline {
    agent any

    tools {
        maven 'M3'  // Используем Maven tool с именем 'M3', которое вы настроили в Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git credentialsId: 'jenkins-ssh', url: 'git@github.com:Zumel-bot/node-app.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install -DskipTests=true'
            }
        }

        stage('Run') {
            steps {
                sh 'java -jar target/*.jar'
            }
        }
    }
}
