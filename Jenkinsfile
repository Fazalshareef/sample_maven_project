pipeline {
    agent any

    tools {
        maven 'Maven-3.9'
        jdk 'JDK-17'
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

