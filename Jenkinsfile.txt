pipeline {
    agent any

    environment {
        GIT_REPO = 'https://github.com/etiamsurgo/IT488_Group2.git'
        BRANCH = 'main' // Replace with the appropriate branch if needed
    }

    stages {
        stage('Clone Repository') {
            steps {
                echo 'Cloning repository...'
                git branch: "${BRANCH}", url: "${GIT_REPO}"
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies...'
                // Replace with your project's dependency installation command
                // Example for Node.js:
                // sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running tests...'
                // Replace with your project's test command
                // Example for Node.js:
                // sh 'npm test'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                // Replace with your project's build command
                // Example for Node.js:
                // sh 'npm run build'
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution finished.'
        }
        success {
            echo 'Pipeline succeeded.'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
