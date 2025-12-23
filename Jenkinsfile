pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment {
        COURSE = "Jenkins"
    }
    options {
        timeout(time: 10, unit: 'MINUTES') 
        disableConcurrentBuilds()
    }
    stages {
        stage('Build') {
            steps {
                script{
                  sh """
                    echo "Building"
                    echo $COURSE
                    env
                    sleep 10
                    """
                }
            }
        }
        stage('Test') {
            steps {
                script{
                    sh """
                    echo "Testing"
                    """
                }
            }
        }
        stage('Deploy') {
            steps {
                script{
                   sh """
                    echo "Deploying"
                    """
                }
            }
        }
    }
    post{
        always{
            echo 'I will always say Hello again!'
            cleanWs()
            }
        success{
            echo 'i will run when i am success'
        }
        failure{
            echo 'i will run when i am failure'
        }
        aborted {
            echo 'pipeline is aborted'
        }        
    }
}