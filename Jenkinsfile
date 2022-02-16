pipeline {
    agent any

    stages {
        stage('Build Image'){
            steps {
                script{
                    dockerapp = docker.build("viniciusesteter/api-produto:${env.BUILD_ID}", '-f ./src/Dockerfile ./src')
                }
            }
        }
        stage('Push Image'){
            steps {
                script {
                    docker.withRegistry('http://registry.hub.docker.com', 'dockerhub')
                        dockerapp.push('latest')
                        dockerapp.push('${env.BUILD_ID}')
                }
            }
        }
    }
}