pipeline {
    agent none

    stages {
        
        stage('compile') {
            agent {
                docker { image 'maven:3.5-jdk-8-alpine' }
            }
            steps {
                sh './mvnw clean package -DskipTests'
            }
        }
    }
}