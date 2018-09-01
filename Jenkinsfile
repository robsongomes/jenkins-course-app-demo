pipeline {
    agent {
        docker 'maven:3.5-alpine'
    }
    stages {
        stage('Maven Checkout') {
            steps {
                git 'https://github.com/robsongomes/jenkins-course-app-demo.git' 
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
                junit '**/target/surefire-reports/TEST-*.xml'
            }
        }
    }
}