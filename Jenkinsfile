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

        stage('Install Dependencies') {
            steps {
                sh 'pip3 install -r requirements.txt || true'
            }
        }

        stage('Run App') {
            steps {
                sh 'python3 main.py'
            }
        }
    }
}