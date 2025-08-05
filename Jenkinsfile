pipeline {
    agent any

    environment {
        VENV = "venv"
    }

    stages {
        stage('Clone GitHub Repo') {
            steps {
                git credentialsId: 'github-https', url: 'https://github.com/ramyavojjala55/Pipelining_pythonApp.git'
            }
        }

        stage('Set Up Python Virtual Environment') {
            steps {
                sh 'python3 -m venv $VENV'
                sh './$VENV/bin/pip install --upgrade pip'
                sh './$VENV/bin/pip install flask pandas numpy tensorflow'
            }
        }

        stage('Run Flask App') {
            steps {
                sh './$VENV/bin/python app.py'
            }
        }
    }
}
