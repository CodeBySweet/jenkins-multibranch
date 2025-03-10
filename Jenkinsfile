pipeline{

    agent any

    stages{
        stage("Build"){
            when{
                anyOf{
                    branch 'featue'
                    branch 'dev'
                    branch 'stage'
                }
            }
            steps{
                echo "building"
            }
        }

        stage("Test"){
            when{
                not{
                    branch 'main'
                }
            }
            steps{
                echo "testing"
            }
        }

        stage("Deploy"){
            when{
                branch 'main'
            }
            steps{
                echo "deploying"
            }
        }
    }

}