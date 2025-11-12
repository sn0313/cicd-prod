pipeline {
    agent any

    stages {
        stage('Deploy to Production') {
            steps {
                echo "Deploying to Production Server..."

                sh '''
                    # Define deployment directory
                    DEPLOY_PATH="/usr/share/nginx/html"

                    if [ -d "$DEPLOY_PATH" ]; then
                        sudo cp index.html $DEPLOY_PATH/index.html
                        echo "Deployment completed successfully."
                    else
                        echo "Error: Deployment path $DEPLOY_PATH does not exist."
                        exit 1
                    fi
                '''
            }
        }
    }

    post {
        success {
            echo 'Deployment to production completed!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}
