pipeline   {
    agent any
    stage {
        stage('Verify Branch') {
            steps {
                echo '$GIT_BRANCH'
            }
        }
        stage('Verify Workspace') {
            steps {
                sh 'git checkout docker_branch'
                echo 'workspace is $WORKSPACE'
            }
        }

    }
}

