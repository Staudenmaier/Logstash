@Library('curl-lib')_
pipeline {
    agent any
    
    stages {
        stage('Download') {
            steps {
                sh 'echo "{\"Klocwork\": \"100\"}" > klocwork.json'
                sh 'echo "{\"Bullseye\": \"300\"}" > bullseye.json'
            }
        }
    }
    post {
        always {
            archiveArtifacts artifacts: 'klocwork.json', onlyIfSuccessful: true
            archiveArtifacts artifacts: 'bullseye.json', onlyIfSuccessful: true
        }
    }

}
curlsend 'klocwork.json'
logstashSend failBuild: false, maxLines: 100, sendArtifact: true

