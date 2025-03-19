pipeline {
    agent any

    environment {
        IMAGE_NAME="python-web-app"
        IMAGE_TAG="latest"
    }

    stages {
        stage("Build Docker image") {
            steps {
                script {
                    sh """
                        cd examples/python-web-app
                        docker build -t ${IMAGE_NAME}:${IMAGE_TAG} .
                    """
                }
            }
        }
        stage("Run Docker image") {
            steps {
                script {
                    sh '''
                        docker run -d -p 8001:8000 ${IMAGE_NAME}:${IMAGE_TAG}
                    '''
                }
            }
        }
    }
}