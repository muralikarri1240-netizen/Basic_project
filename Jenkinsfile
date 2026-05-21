pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
            }
        }
        stage('Build') {
            steps {
                echo 'Building with Maven'
                bat 'mvn -B clean package'
            }
        }
        stage('Test') {
            steps {
                echo 'Running unit tests'
                bat 'mvn -B test'
            }
        }
        stage('deploy') {
            steps {
                echo 'Artifactory upload'
                bat 'mvn deploy'
            }
        }
        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }

    post {
        always {
            junit 'target/surefire-reports/*.xml'
        }
        success {
            echo 'Build succeeded.'
        }
        failure {
            echo 'Build failed.'
        }
    }
}
