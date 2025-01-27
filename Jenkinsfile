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
                    sh 'git config --global user.name "himanshudogra"'
                    sh 'git config --global user.email "himanshudogra96@gmail.com"'

                    // Add and commit changes
                    sh 'git add .'
                    sh 'git commit -m "Add example.txt file"'

                    // Explicitly set credentials for git push
                    sh '''
                    git remote set-url origin https://himanshudogra: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@github.com/himanshudogra/my_project.git
                    git push origin master
                    '''
                }
            }
        }
    }
}
