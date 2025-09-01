pipeline
{
    agent any
    
    stages{
        stage('Git Checkout')
        {
            steps
            {
                echo 'This is Git Checkout Stage'
                git branch:'main',url:'https://github.com/lukesh-kalam/jenkins.git'
                echo "Checked out branch: ${env.BRANCH_NAME}"
            }
            
        }
        stage('Run Code')
        {
            when {
                    expression {
                        BRANCH_NAME='main'
                    }
            }
            steps
            {
                echo 'Run Python Code'
                powershell  'python hello.py'
            }
            
        }
    }
}
