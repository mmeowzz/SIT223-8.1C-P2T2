pipeline {
    agent any
    environment {
        DEV_EMAIL = 'chanulyafernando18@gmail.com'
    }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        post {
        success {
            emailext(
                subject: "Tests Passed: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "The test stage was successful.\nSee Jenkins console: ${env.BUILD_URL}",
                to: "${env.DEV_EMAIL}",
                attachLog: true
            )
        }
        failure {
            emailext(
                subject: "Tests Failed: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "The test stage failed.\nSee Jenkins console: ${env.BUILD_URL}",
                to: "${env.DEV_EMAIL}",
                attachLog: true
            )
        }
    }
    }
}
