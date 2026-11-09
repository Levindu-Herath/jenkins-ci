pipeline{
    agent any

    parameters{
        choice(name:'VERSION',choices:['1.1.0','1.2.0','1.3.0'],description:'Select the version to build')
        booleanParam(name:'executeTests',defaultValue:true,description:'Execute tests after build')
    }

    stages{
        stage("build"){

            steps{
                echo "Building the project"
                echo "building version ${NEW_VERSION}"
            }
        }
        stage("test"){
            when {
                expression{
                    params.executeTests == true
                }
            }
            steps{
                echo "Running tests"
            }
        }
        stage("deploy"){
            steps{
                echo "Deploying the project"
                echo "Deploying version ${params.VERSION}"
            }
        }
    }
}