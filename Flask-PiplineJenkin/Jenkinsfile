pipeline {
    agent any

    stages {
        stage('Setup') {
            steps {
                sh 'python3 -m venv venv'
                sh './venv/bin/pip install flask'
            }
        }

        stage('Run Flask') {
            steps {
                sh 'nohup ./venv/bin/python app.py &'
            }
        }

        stage('Test') {
            steps {
                sh 'curl http://localhost:5000'
            }
        }
    }
}
