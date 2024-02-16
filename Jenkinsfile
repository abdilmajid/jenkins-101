pipeline {
    agent { 
        node {
            label 'docker-agent-python'
            }
      }
    triggers {
        githubPush() 
    }
    stages {
        stage('Build') {
            steps {
                echo "Building Stage2..."
                sh '''
                cd myapp
                pip install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing Stage2..."
                sh '''
                cd myapp
                python3 hello.py
                python3 hello.py --name=Abdil
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver Stage2...'
                sh '''
                echo "doing delivery stuff again.."
                '''
            }
        }
    }
}
