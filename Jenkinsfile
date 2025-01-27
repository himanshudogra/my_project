pipeline {
    agent any  // This ensures the pipeline will run on any available agent

    stages {
        stage('Checkout') {
            steps {
                node {
                    // Checkout the repository
                    git url: 'https://github.com/himanshudogra/my_project.git', credentialsId: 'github-credentials'
                }
            }
        }
        // Add other stages as needed
    }
}
