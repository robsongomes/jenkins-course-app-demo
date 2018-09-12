pipeline {
    agent {
        docker { image '3.5-jdk-8-alpine' }
    }

    stages {
        stage('clone') {
            git 'https://github.com/robsongomes/jenkins-course-app-demo.git'
        }
        
        stage('compile') {
            sh './mvnw clean package -DskipTests'
        }
    }
}