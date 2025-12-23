pipeline {
    agent {
        docker {
            image 'maven:3.9.9-eclipse-temurin-17'
        }
    }

    stages {

        stage('SCM') {
            steps {
                echo 'Checking out source code from Git'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application'
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                echo 'Running unit tests'
                sh 'mvn test'
            }
        }

        stage('Build Completed') {
            steps {
                echo '✅ Build and Test stages completed successfully'
            }
        }
    }

    post {
        failure {
            echo '❌ Pipeline failed'
        }
        success {
            echo '🎉 Pipeline executed successfully'
        }
    }
}

