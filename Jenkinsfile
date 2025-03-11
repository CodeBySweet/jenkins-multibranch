pipeline{

    agent any

    parameters{
        booleanParam(name: 'DEPLOY', description: 'Is deploying:', defaultValue: false)
    }

    stages{
        stage("Build"){
            when{
                anyOf{
                    branch 'feature'
                    branch 'dev'
                }
            }
            steps{
                echo "building"
            }
        }

        stage("Test"){
            // when{
            //     not{
            //         branch 'main'
            //     }
            
            steps{
                script{
                    if(env.BRANCH_NAME != 'main'){
                        echo "tetsing, the branch name is ${BRANCH_NAME}"
                    }else{
                        echo 'Testing is not allowed in main'
                    }
                }
            }
        }

        stage("Deploy"){
            // when{
            //     branch 'main'
            // }
            when{
                expression{
                    env.BRANCH_NAME == 'main' || params.DEPLOY
                }
            }
            steps{
                echo "deploying 2"
            }
        }
    }

}