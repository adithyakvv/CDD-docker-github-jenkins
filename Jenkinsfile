pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/adithyakvv/CDD-docker-github-jenkins.git'
            }
        }

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