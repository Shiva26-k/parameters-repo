pipeline {
    agent {
        label 'java-slave'
    }
    environment {
        DEPLOY_TO = 'stage'
    }
    stages {
        stage('Debug Info') {
            steps {
                echo "Current Branch: ${env.BRANCH_NAME}"
                echo "DEPLOY_TO Environment Variable: ${env.DEPLOY_TO}"
            }
        }
        stage('Build') {
            when {
                anyOf {
                    branch 'prod'
                    environment name: 'DEPLOY_TO', value: 'release'
                }
            }
            steps {
                echo "Build stage is running"
            }
        }
    }
    post {
        always {
            echo "job success by using anyof option"
        }
        success {
            echo "***successful to build stages***"
        }
        failure {
            echo "***failure to build stages***"
        }
    }
}
