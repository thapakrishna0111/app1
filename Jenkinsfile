pipeline {

    environment {
        registry = "kt0111/app1"
        registryCredential = 'DockerHub'
    }
   
    agent any
    stages {
        stage('Verify Branch') {
            steps {
                echo '$GIT_BRANCH'
            }
        }
        stage('Build Image') {
            steps {
                scripts {
                    docker.build registry + ":$BUILD_NUMBER"
                }  
            }
        }
    }
}

