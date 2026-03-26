pipeline {
    agent {
        label 'jenkins-inbound-agent'
    }

    stages {
        stage('Clone') {
            steps {
                checkout scm
            }
        }

        stage('Setup Python Env') {
            steps {
                sh '''
                python3 -m venv venv
                . venv/bin/activate
                pip install --upgrade pip
                pip install -r requirements.txt || true
                '''
            }
        }

        stage('Run App') {
            steps {
                sh '''
                . venv/bin/activate
                python main.py
                '''
            }
        }
    }
}