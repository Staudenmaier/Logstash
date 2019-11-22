pipeline {
    agent any
    
    stages {
        stage('Download') {
            steps {
                sh 'echo "artifact file" > generatedFile.txt'
            }
        }
    }
    post {
        always {
            archiveArtifacts artifacts: 'generatedFile.txt', onlyIfSuccessful: true
        }
    }

    logstash {
            echo '{"Type": "KLST","window": {"title": "Sample Konfabulator Widget","name": "main_window","width": 500,"height": 500}}'
    }
}
