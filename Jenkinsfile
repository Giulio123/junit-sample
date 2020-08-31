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
                sh './gradlew test'
            }

        }
    }

    post {
        always {
            archiveArtifacts artifacts: '**/build/libs/**/*.jar', fingerprint: true
            junit '**/build/test-results/test/*.xml'
        }
    }
}