pipeline {
    agent any

    stages {

        stage('Build Project') {
            steps {
                bat '.\\mvnw clean package'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t springboot-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker run -d -p 8080:8080 springboot-app'
            }
        }

    }
}