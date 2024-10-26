// Jenkinsfile
pipeline {
    agent any
    environment {
        DOCKER_HUB_REPO = 'saumyaswami/my-java-app'
    }
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("${DOCKER_HUB_REPO}")
                }
            }
        }
        stage('Push to Docker Hub') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', 'docker-hub-credentials') {
                        docker.image("${DOCKER_HUB_REPO}").push()
                    }
                }
            }
        }
    }
}
