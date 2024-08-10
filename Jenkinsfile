pipeline {
    agent none
    stages {
        stage('Build and Run Flask App') {
            agent {
                docker { image 'python:3.9-alpine' }
            }
            steps {
                script {
                    // Clone the repository
                    checkout scm
                    
                    // Build Docker image and run the container on Jenkins host
                    sh '''
                    docker build -t flask-app .
                    docker run -d -p 5000:5000 flask-app
                    '''
                }
            }
        }
    }
}
