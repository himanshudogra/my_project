pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from your Git repository
                git 'https://github.com/himanshudogra/my_project.git'
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
                    // Configure Git user (if needed)
                    sh 'git config --global user.name "himanshudogra"'
                    sh 'git config --global user.email "himanshudogra96@gmail.com"'

                    // Add and commit changes
                    sh 'git add .'
                    sh 'git commit -m "Add example.txt file"'
                    
                    // Push changes to the repository
                    sh 'git push origin main'
                }
            }
        }
    }
}
