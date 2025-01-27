pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Ensure SSH key is loaded into the SSH agent
                sshagent(['github-ssh-key']) {
                    // Clone the repository using SSH
                    git 'git@github.com:himanshudogra/my_project.git'
                }
            }
        }
        // Add your other stages here like Build, Test, etc.
    }
}
