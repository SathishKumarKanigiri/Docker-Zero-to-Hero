pipeline {
    agent master

    stages {
        stage("Build Docker image") {
            steps {
                script {
                    sh '''
                        cd examples/python-web-app
                        docker build -t python-web-app:latest .
                    '''
                }
            }
        }
    }
}