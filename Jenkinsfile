pipeline {
    agent any

    environment {
        APP_NAME = 'my-app'
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Cloning the repository...'
                git branch: 'main', url: 'https://github.com/your-username/your-repo.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                // For example: Compile a Java/Maven app
                sh './mvnw clean package'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh './mvnw test'
            }
        }
    }

    post {
        always {
            echo 'This will always run (cleanup, archive, etc.)'
        }
        success {
            echo 'Build succeeded!'
        }
        failure {
            echo 'Build failed!'
        }
        unstable {
            echo 'Build is unstable (e.g., some tests failed)'
        }
        changed {
            echo 'Build status changed compared to last time.'
        }
    }
}
