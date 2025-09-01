pipeline {
    agent any
    stages {
        stage('Run main branch code') {
            when {
                expression { env.BRANCH_NAME = 'main' }
            }
            steps {
                echo "Running code from MAIN branch"
                powershell "python hello.py"
            }
        }
        stage('Switch to Lukesh Branch')
        {
            powershell 'git switch lukesh'
        }

        stage('Run lukesh branch code') {
            when {
                expression { env.BRANCH_NAME = 'lukesh' }
            }
            steps {
                echo "Running code from LUKESH branch"
                powershell "python lukesh_branch.py"
            }
        }
    }
}
