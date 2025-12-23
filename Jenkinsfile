pipeline {
    agent {
        docker {
            image 'maven:3.9.9-eclipse-temurin-17'
        }
    }

    stages {
        stage('Build & Test') {
            steps {
                sh 'mvn clean test'
            }
        }
    }

    post {
        success {
            echo '✅ Build and tests successful'
        }
        failure {
            echo '❌ Build or tests failed'
        }
    }
}

