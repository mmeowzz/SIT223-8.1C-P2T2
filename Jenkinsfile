pipeline {
    agent any
    environment {
        DEV_EMAIL = 'youlovemylife06@gmail.com'
    }
    stages {
        stage('Test') {
            steps {
                echo 'Running tests...'
            }
            post {
                always {
                    emailext(
                        subject: "Test Stage: ${currentBuild.currentResult} - ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                        body: """Hello,  
                        
The Test stage finished with status: ${currentBuild.currentResult}  

See details: ${env.BUILD_URL}  

Regards,  
Jenkins
""",
                        to: "${env.DEV_EMAIL}",
                        attachLog: true
                    )
                }
            }
        }
    }
}
