pipeline {
    agent { 
        node {
            label 'docker-agent-python'
            }
      }
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building"
                sh '''
                cd myapp
                ls
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing"
                sh '''
                echo "doing test stuff.."
                python3 ../hello.py
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver'
                sh '''
                echo "doing delivery stuff.."
                python3 --version
                docker --version
                docker-compose --version
                '''
            }
        }
    }
}