pipeline {
    agent any

    environment {
        // Define environment variables (e.g., deployment directory, node environment)
        NODE_ENV = 'production'
        // DEPLOY_DIR = '/path/to/your/deployment/directory'
    }

    stages {

        stage('Install Dependencies') {
            steps {
                script {
                    // Install Node.js dependencies
                    echo 'Installing depedencies!'
                    sh 'npm install'
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    // Run tests with npm (adjust for your test framework, e.g., Mocha, Jest)
                    echo 'Runnin Tests!'
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    // Add any build steps needed (e.g., webpack, babel transpiling)
                    // Example (optional):
                    echo 'Building!'
                    // sh 'npx webpack --config webpack.prod.js'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Deploying using SSH or another method to your remote server
                    // For example, use SCP (secure copy) to copy files to the server
                    // sh 'scp -r ./ your-user@your-server:/path/to/deployment/directory'
                    echo 'Deploying!'
                    // Example: Restart the Node.js app using PM2
                    // sh 'ssh your-user@your-server "pm2 restart your-app-name"'
                    
                    // You can also use other deployment methods (Docker, Kubernetes, etc.)
                }
            }
        }
    }

    post {
        always {
            // Always run cleanup or final notifications here
            echo 'Pipeline finished.'
        }

        success {
            // Actions after a successful deployment
            echo 'Deployment was successful!'
        }

        failure {
            // Actions if the pipeline fails
            echo 'Deployment failed!'
        }
    }
}
