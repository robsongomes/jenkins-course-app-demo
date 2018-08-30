pipeline {
    agent any

    tools {
        maven 'maven'
    }
    stages {
        stage('Maven Checkout') {
            steps {
                git 'https://github.com/robsongomes/jenkins-course-app-demo.git' 
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}