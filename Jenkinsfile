pipeline {
    agent any
    stages {
        stage('Check emailext') {
            steps {
                script {
                    echo "About to call emailext..."
                    emailext(
                        subject: "emailext test",
                        body: "This is just to confirm emailext works.",
                        to: "youlovemylife06@gmail.com"
                    )
                }
            }
        }
    }
}
