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
                pip install -r requirements.txt
                # python3 hello.py --name Anderson
                ls
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing"
                sh '''
                echo "doing test stuff.."
                ls
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