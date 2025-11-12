pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                echo "Deploying production code..."
                sh 'sudo cp index.html /usr/share/nginx/html/index.html'
            }
        }
    }

    post {
        success { echo "Production deployment successful!" }
        failure { echo "Production deployment failed!" }
    }
}
