pipeline {
    agent any
    stages {
        stage("Lint HTML") {
            steps {
                sh "tidy -q -e *.html"
            }
        }
        stage("Upload to AWS") {
            steps {
                withAWS(region:'us-east-1',credentials:'aws-jenkins') {
                    s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'udacity-static-s3')
                }
            }
        }
    }
}