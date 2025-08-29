pipeline {
    agent any
    environment {
        DEV_EMAIL = 'youlovemylife06@gmail.com'
    }
    stages {
        // Dummy Test stage
        stage('Test') {
            steps {
                echo 'Running tests...'
            }
            post {
                success {
                    emailext(
                        subject: "Test Passed: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                        body: "The Test stage was successful.\nSee Jenkins console: ${env.BUILD_URL}",
                        to: "${env.DEV_EMAIL}",
                        attachLog: true
                        // Add this line to use credentials
                        from: 'chanulyafernando18@gmail.com',
                        replyTo: 'chanulyafernando18@gmail.com',
                        mimeType: 'text/plain'
                    )
                }
                failure {
                    emailext(
                        subject: "Test Failed: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                        body: "The Test stage failed.\nSee Jenkins console: ${env.BUILD_URL}",
                        to: "${env.DEV_EMAIL}",
                        attachLog: true
                    )
                }
            }
        }

        // Dummy Security Scan stage
        stage('Security Scan') {
            steps {
                echo 'Running security scan...'
            }
            post {
                success {
                    emailext(
                        subject: "Security Scan Passed: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                        body: "The Security Scan stage was successful.\nSee Jenkins console: ${env.BUILD_URL}",
                        to: "${env.DEV_EMAIL}",
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        subject: "Security Scan Failed: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                        body: "The Security Scan stage failed.\nSee Jenkins console: ${env.BUILD_URL}",
                        to: "${env.DEV_EMAIL}",
                        attachLog: true
                    )
                }
            }
        }
    }
}
