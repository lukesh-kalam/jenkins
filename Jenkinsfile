pipeline
{
    agent any
    stages
    {
        stage('git checkout main')
        {
            when {
                    expression {
                        BRANCH_NAME='main'
                    }
            }
            steps
            {
                echo "Here I am checkingout main Branch"
                echo "Running Hello.py file"
                powershell "python hello.py"
            }
        }
        stage('git checkout lukesh')
        {
            when {
                expression {
                    BRANCH_NAME ='lukesh'
                }
            }
            steps{
                echo "Here I am checkingout lukesh Branch"
                echo "Running lukesh_branch.py file"
                powershell "python lukesh_branch.py"
            }
        }
    }

}
