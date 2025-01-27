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
                // You can replace this with the actual build command, e.g., `mvn clean install` or `python setup.py install`
                sh 'echo "Building project..."'
            }
        }
        
        stage('Test') {
            steps {
                echo 'Running tests...'
                // Replace with the actual test command (e.g., `mvn test` or `pytest`)
                sh 'echo "Running tests..."'
            }
        }
        
        stage('Make a Change in Repo') {
            steps {
                echo 'Making a simple change in the repository...'
                sh 'echo "This is a new change" > change.txt'  // This creates a new file
                sh 'git add change.txt'  // Add the new file to git
                sh 'git commit -m "Added change.txt"'  // Commit the change
                sh 'git push origin master'  // Push the changes (adjust if needed)
            }
        }
        
        stage('Clean Up') {
            steps {
                echo 'Cleaning up...'
                // Any cleanup tasks if required
            }
        }
    }
}

