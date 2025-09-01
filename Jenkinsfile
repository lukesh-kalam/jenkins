pipeline {
    agent any
    stages {
        stage('Run main branch code') {
            when {
                branch 'main'
            }
            steps {
                echo "Running code from MAIN branch"
                powershell "python hello.py"
            }
        }

        stage('Switch to lukesh branch') {
            when {
                branch 'main'   // Only switch if we started from main
            }
            steps {
                script {
                    checkout([
                        $class: 'GitSCM',
                        branches: [[name: '*/lukesh']],
                        doGenerateSubmoduleConfigurations: false,
                        extensions: [],
                        userRemoteConfigs: [[url: 'https://github.com/lukesh-kalam/jenkins.git']]
                    ])
                }
                steps {
                echo "Running code from LUKESH branch"
                powershell "python lukesh_branch.py"
            }
            }
        }

        stage('Run lukesh branch code') {
            when {
                branch 'main'   // Only run if we switched from main
            }
            steps {
                echo "Running code from LUKESH branch"
                powershell "python lukesh_branch.py"
            }
        }
    }
}
