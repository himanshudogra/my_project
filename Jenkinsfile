pipeline {
    agent any

    environment {
        GIT_CREDENTIALS = credentials('github-credentials')  // Add this line for credentials
        GIT_USERNAME = credentials('github-credentials').username  // Get GitHub username
        GIT_TOKEN = credentials('github-credentials').password  // Get GitHub token
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

                    // Set remote URL with credentials (GitHub username and token)
                    sh '''
                    git remote set-url origin https://$GIT_USERNAME:$GIT_TOKEN@github.com/himanshudogra/my_project.git
                    git push origin master
                    '''
                }
            }
        }
    }
}
