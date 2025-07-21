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
       
    }
}
