pipeline {
    agent none

    stages {
        
        stage('compile') {
            agent {
                docker { image 'maven:jdk-8-alpine' }
            }
            steps {
                sh './mvnw clean package -DskipTests'
            }
        }
    }
}