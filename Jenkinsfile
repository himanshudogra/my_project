pipeline {
    agent any
    
    stages {
        stage('Clone Repository') {
            steps {
                echo 'Cloning the repository...'
                git 'https://github.com/himanshudogra/my_project.git'
            }
        }
        
        stage('Build') {
            steps {
                echo 'Building project...'
                sh 'echo "Building project..."'
            }
        }
        
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'echo "Running tests..."'
            }
        }
        
        stage('Make a Change in Repo') {
            steps {
                echo 'Making a simple change in the repository...'
                
                // Set Git user identity for Jenkins
                sh 'git config --global user.name "Jenkins"'
                sh 'git config --global user.email "jenkins@example.com"'
                
                // Make a simple change
                sh 'echo "This is a new change" > change.txt'  
                sh 'git add change.txt'
                sh 'git commit -m "Added change.txt"'
                sh 'git push origin master'  // Push changes (make sure you have permissions)
            }
        }
        
        stage('Clean Up') {
            steps {
                echo 'Cleaning up...'
            }
        }
    }
}

