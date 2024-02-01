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
                echo "doing build stuff.."
                python3 --version
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing"
                sh '''
                echo "doing test stuff.."
                docker --version
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver'
                sh '''
                echo "doing delivery stuff.."
                docker-compose --version
                '''
            }
        }
    }
}