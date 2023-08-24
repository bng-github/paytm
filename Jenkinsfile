pipeline {
    agent any
    
    environment {
        DOCKER_IMAGE_NAME = "my-docker-image"
        DOCKERFILE_PATH = "Dockerfile" // Update this with your Dockerfile's path
    }
    
    stages {
        
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build(DOCKER_IMAGE_NAME, "-f ${DOCKERFILE_PATH} .")
                }
            }
        }
    }
    
    post {
        success {
            echo "Docker image build and push successful"
        }
        failure {
            echo "Docker image build and/or push failed"
        }
    }
}
