pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                script {
                    // Ensure the .ssh directory exists
                    sh 'mkdir -p ~/.ssh'
                    
                    // Add GitHub's SSH key to known_hosts
                    sh 'ssh-keyscan github.com >> ~/.ssh/known_hosts'
                }
                sshagent(['github-ssh-key']) {
                    // Clone the repository using SSH
                    git 'git@github.com:himanshudogra/my_project.git'
                }
            }
        }
        // Other stages (Build, Test, etc.)
    }
}
