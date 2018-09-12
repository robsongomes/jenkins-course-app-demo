pipeline {
    agent none

    stages {
        stage('clone') {
            git 'https://github.com/robsongomes/jenkins-course-app-demo.git'
        }
        
        stage('compile') {
            agent {
                docker { image '3.5-jdk-8-alpine' }
            }
            steps {
                sh './mvnw clean package -DskipTests'
            }
        }
    }
}