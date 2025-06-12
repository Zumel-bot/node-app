pipeline {
    agent any
tools {
    maven 'M3' // Используем Maven tool с именем 'M3'
}

stages {
    stage('Checkout') {
        steps {
            git credentialsId: 'your-git-credentials', url: 'git@github.com:your-username/simple-maven-m3-project.git'  // Используйте ваши учетные данные Git
        }
    }
    stage('Build') {
        steps {
            sh 'mvn clean install'
        }
    }
    stage('Run') {
        steps {
            sh 'java -jar target/simple-maven-m3-project-1.0-SNAPSHOT.jar'
        }
    }
}
