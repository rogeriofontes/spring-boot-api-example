pipeline {
    agent any

    triggers {
        pollSCM '* * * * *'
    }
    stages {
        
        stage('Build') {
            steps {
                sh './gradlew assemble'
            }
        }
        
        stage('Test') {
            steps {
                sh './gradlew test'
            }
        }
        stage('Build Docker image') {
            steps {
                sh 'docker-compose up -d'
                sh 'docker running on port 8080'
            }
        }
    }
}

