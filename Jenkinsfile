pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/himanshudogra/my_project.git'
            }
        }
        stage('Build') {
            steps {
                // Replace this with your build command
                sh 'echo "Building project..."'
            }
        }
        stage('Test') {
            steps {
                // Replace this with your test command
                sh 'echo "Running tests..."'
            }
        }
        stage('Archive') {
            steps {
                // Replace this with your artifact location
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
            }
        }
    }
}

