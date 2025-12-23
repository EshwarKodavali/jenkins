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
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'DEPLOY', defaultValue: false, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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