pipeline {
    agent any  // Runs on any available agent

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/ugesh03/testrepo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'echo Building the application...'
                sh 'mvn clean package'  // Example for Java projects
            }
        }

        stage('Test') {
            steps {
                sh 'echo Running tests...'
                sh 'mvn test'  // Run test cases
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo Deploying application...'
                sh 'scp target/*.jar ubuntu@54.152.35.55:/var/www/html/'  // Example deployment
            }
        }
    }
}
