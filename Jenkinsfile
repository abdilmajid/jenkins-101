pipeline {
    agent { 
        node {
            label 'docker-agent-python'
            }
      }
    triggers {
        // githubPush()
        pollSCM '*/5 * * * *' 
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
                python3 hello.py
                python3 hello.py --name=Brad
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver Stage...'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}
