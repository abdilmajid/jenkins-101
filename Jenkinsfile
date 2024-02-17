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
                echo "Building Stage..."
                sh '''
                cd myapp
                pip install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing Stage..."
                sh '''
                cd myapp
                which python3
                python3 hello.py
                python3 hello.py --name=Abdil
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver Stage...'
                sh '''
                echo "doing delivery stuff again.."
                '''
            }
        }
    }
}
