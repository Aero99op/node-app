pipeline {
agent any
environment {
    IMAGE_NAME = "nodeapp"
    CONTAINER_NAME = "nodeapp-container"
}
stages {

    stage('Build Docker Image') {
        steps {
            sh 'docker build -t ${IMAGE_NAME}:${BUILD_NUMBER} .'
        }
    }
    stage('Stop Old Container') {
        steps {
            sh '''
            docker stop ${CONTAINER_NAME} || true
            docker rm ${CONTAINER_NAME} || true
            '''
        }
    }
}
