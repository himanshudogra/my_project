pipeline {
    agent any

    environment {
        GIT_CREDENTIALS = 'github-credentials'  // Reference the credentials ID
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from your Git repository using credentials
                git url: 'https://github.com/himanshudogra/my_project.git', credentialsId: GIT_CREDENTIALS
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
                    withCredentials([usernamePassword(credentialsId: 'github-credentials', usernameVariable: 'GIT_USERNAME', passwordVariable: 'GIT_TOKEN')]) {
                        sh '''
                        git remote set-url origin https://$GIT_USERNAME:$GIT_TOKEN@github.com/himanshudogra/my_project.git
                        git push origin master
                        '''
                    }
                }
            }
        }
    }
}
