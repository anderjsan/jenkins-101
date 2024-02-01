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
                python3 -m venv test_env
                test_env\Scripts\activate
                pip install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing"
                sh '''
                echo "doing test stuff.."
                ls
                # python3 hello.py --name Anderson
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