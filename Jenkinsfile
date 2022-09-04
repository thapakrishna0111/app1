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
                sh '''cd azure-vote/
                docker.withRegistry(\'https://index.docker.io/v1/\', \'DockerHub\') {
                    def customImage = docker.build("kt0111/docker_app:${env.BUILD_ID}")
                    customImage.push()'''
            }
        }
    }
}

