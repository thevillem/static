pipeline {
    agent any
    stages {
        stage("Upload to AWS") {
            steps {
                withAWS(region:'us-east-1',credentials:'aws-jenkins') {
                    s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'udacity-static-s3')
                }
            }
        }
    }
}