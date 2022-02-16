pipeline {
    agent any

    stages {
        stage('Build Image'){
            steps {
                script{
                    dockerapp = docker.build("viniciusesteter/api-produto", '-f ./src/Dockerfile ./src')
                }
            }
        }
    }
}