pipeline {
    agent any

    environment {
        GIT_CREDENTIALS = credentials('github-credentials')  // Add this line for credentials
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from your Git repository using credentials
                git url: 'https://github.com/himanshudogra/my_project.git', credentialsId: 'github-credentials'
            }
        }
        stage('Modify Files') {
            steps {
                // Add or modify files (Example)
                script {
                    writeFile file: 'example.txt', text: 'This is an example file.'
                }
            }
        }
        stage('Git Commit and Push') {
            steps {
                script {
                    // Configure Git user
                    sh 'git config --global user.name "jenkins"'
                    sh 'git config --global user.email "himanshudogra96@gmail.com"'

                    // Add and commit changes
                    sh 'git add .'
                    sh 'git commit -m "Add example.txt file"'

                    // Push changes to the master branch
                    sh 'git push origin master'
                }
            }
        }
    }
}
