pipeline {
    agent {
        label "build-agent"
    }

    environment {
        // Define environment variables if needed
        NODEJS_HOME = tool name: 'NodeJS', type: 'jenkins.plugins.nodejs.tools.NodeJSInstallation'
        // Add other environment variables as needed
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from your version control system (e.g., Git)
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                // Install Node.js dependencies
                bat 'npm install'
            }
        }


                stage('Build-3') {
            steps {
                // Build the React app
                bat 'npm install -g serve'
            }
        }

                stage('Build-4') {
            steps {
                // Build the React app
                bat 'serve -s build'
            }
        }

        stage('Archive Artifacts') {
            steps {
                // Archive the build artifacts (e.g., the 'build' directory)
                archiveArtifacts artifacts: 'build/**/*', fingerprint: true
            }
        }
    }

    post {
        success {
            // Add post-build actions if needed
            echo 'Build successful!'
        }

        failure {
            // Add actions to take on build failure
            echo 'Build failed!'
        }
    }
}
