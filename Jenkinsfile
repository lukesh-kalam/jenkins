pipeline {
    agent any
    stages {
        stage('Debug Env') {
            steps {
                echo "Branch Name: ${env.BRANCH_NAME}"
                echo "GIT_BRANCH: ${env.GIT_BRANCH}"
            }
        }
        stage('Run main branch code') {
            when {
                expression { env.BRANCH_NAME == 'main' || env.GIT_BRANCH == 'origin/main' }
            }
            steps {
                echo "Running code from MAIN branch"
                powershell "python hello.py"
            }
        }
        stage('Run lukesh branch code') {
            when {
                expression { env.BRANCH_NAME == 'lukesh' || env.GIT_BRANCH == 'origin/lukesh' }
            }
            steps {
                echo "Running code from LUKESH branch"
                powershell "python lukesh_branch.py"
            }
        }
    }
}
