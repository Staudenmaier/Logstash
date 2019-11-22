pipeline {
    agent any
    
    stages {
        stage('Download') {
            steps {
                sh 'echo "{\"Klockwork\": \"100\"}" > generatedFile.txt'
            }
        }
    }
    post {
        always {
            archiveArtifacts artifacts: 'generatedFile.txt', onlyIfSuccessful: true
        }
    }

}
logstashSend failBuild: false, maxLines: 100, sendArtefact: true

