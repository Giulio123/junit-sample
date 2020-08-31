pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh './gradlew build'
            }
        }
        stage('Test') {
            steps {
                sh './gradlew check'
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'application/build/libs/**/*.jar', fingerprint: true
            junit 'application/build/test-results/test/*.xml'
        }
    }
}