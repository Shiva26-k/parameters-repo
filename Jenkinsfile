pipeline{
    agent {
        label 'java-slave'
    }
    stages{
        stage('Build'){
            steps{
                echo "Build is success"
            }
        }
        stage('Scans'){
            parallel{
                    stage('SonarScans'){
                steps{
                    echo "sonarscan is running"
                    sleep 15
                }
                }
                stage('FortifyScans'){
                    steps{
                        echo "Fortifyscan is executing "
                        sleep 15
                    }
                }
                stage('PrismaScans'){
                    steps{
                        echo "Prismascan is executing"
                        sleep 15
                    }
                }
            }
        }
       stage('DeplotTodev'){
        steps{
            echo "Deploying to dev env"
        }
       }
       stage('DeployToTEst'){
        steps{
            echo "Deploying to Test env"
        }
       }
       stage('DeployToStage'){
        steps{
            echo "Deploying to stage env"
        }
       }
       stage('DeployToProd'){
        options{
                timeout (time: 300 , unit: 'SECONDS')
        }
        input{
            message "Deploy to prod ?"
            ok 'yes'
            submitter 'Shiva,rakesh' //who should be having access to approve 
        }
        steps{
            echo "Deploying to prod env"
        }
       }
    }
}
