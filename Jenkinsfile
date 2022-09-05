pipeline {
    agent any
    stages {
        stage('Verify Branch') {
            steps {
                echo '$GIT_BRANCH'
            }
        }
        stage('Verify Workspace') {
            steps {
                echo 'workspace is $WORKSPACE'
                sh 'cd azure-vote/'
                docker.withRegistry('https://registry.example.com', 'DockerHub') {
                    def customImage = docker.build("kt0111/docker_app:${env.BUILD_ID}")
                    customImage.push()
                }
            }
        }
    }
}

