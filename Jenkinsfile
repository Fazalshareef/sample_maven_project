pipeline {
    agent {
        docker {
            image 'maven:3.9.9-eclipse-temurin-17'
        }
    }

    stages {

        stage('SCM') {
            steps {
                checkout scm
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

        stage('Build Completed') {
            steps {
                echo 'Build and Test stages completed'
            }
        }
    }

    post {

        success {
            // Email Notification
            emailext(
                subject: "SUCCESS: Jenkins Build #${BUILD_NUMBER}",
                body: """
                Build Successful ✅
                
                Job: ${JOB_NAME}
                Build Number: ${BUILD_NUMBER}
                URL: ${BUILD_URL}
                """,
                to: "mohammedfazalshareef@gmail.com"
            )

            // Slack Notification
            slackSend(
                channel: '#jenkins-notifications',
                color: 'good',
                message: "✅ SUCCESS: ${JOB_NAME} #${BUILD_NUMBER} \n${BUILD_URL}"
    		tokenCredentialId: 'slack-webhook'
            )
        }

        failure {
            // Email Notification
            emailext(
                subject: "FAILED: Jenkins Build #${BUILD_NUMBER}",
                body: """
                Build Failed ❌
                
                Job: ${JOB_NAME}
                Build Number: ${BUILD_NUMBER}
                URL: ${BUILD_URL}
                """,
                to: "dev-team@example.com"
            )

            // Slack Notification
            slackSend(
                channel: '#build-alerts',
                color: 'danger',
                message: "❌ FAILED: ${JOB_NAME} #${BUILD_NUMBER} \n${BUILD_URL}"
            )
        }
    }
}

