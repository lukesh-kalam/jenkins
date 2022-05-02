pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('lukesh'){
            steps{
                echo 'Hello Lukesh Kumar'
            }
        }
        stage('kumar parallel')
        {
            steps{
                parallel(
                    'First stage':{
                        echo "Good Morning Team"
                    },
                    'Second Stage':{
                        echo "Good Morning Fame"
                    }
                    )
            }
        }
    }
}
