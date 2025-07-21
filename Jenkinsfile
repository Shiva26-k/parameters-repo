pipeline{
    agent {
        label 'java-slave'
    }
    parameters{
        string(name :'APPLICATION_NAME', description:'Enter your application name',defaultValue: 'i27-app')
        booleanParam(name: 'RUN_TESTS', description: 'would you like run tests ?' , defaultValue: true)
        choice(name: 'ENV' , description:'which env should i deploy ?',choices: ['dev','test','prod'])
        password(name: 'PASSWORD', description:'Enter a passsword', defaultValue:'SECRET')

    } 
    stages{
        stage('Build'){
            steps{
                echo "My application name is : ${params.APPLICATION_NAME}"
                echo "Are testing runnig ? :${params.RUN_TESTS}"
                echo "Deploying to ***${params.ENV}***"
                echo "password entered : ${params.PASSWORD}"

            }
        }
    }
}
