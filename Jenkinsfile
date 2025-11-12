pipeline {
    agent any

    stages {
        stage('Deploy to Production') {
            steps {
                echo "Deploying latest index.html to Nginx web root..."
                sh '''
                    # Copy new HTML into Nginx directory
                    sudo cp index.html /usr/share/nginx/html/index.html

                    # Optional: verify deployment
                    echo "Current deployed version:"
                    head -n 3 /usr/share/nginx/html/index.html
                '''
            }
        }
    }

    post {
        success {
            echo 'Deployment to production completed successfully!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}
