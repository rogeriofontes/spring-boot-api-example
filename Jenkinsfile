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
    }
    stage('Run App'){
        runApp()
    }
}

def runApp(){
    sh "docker-compose up -d"
    echo "Application started"
}
