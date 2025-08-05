pipeline {
    agent any

    environment {
        VENV = "venv"
    }

    stages {
        stage('Clone GitHub Repo') {
            steps {
                git 'https://github.com/ramyavojjala55/your-repo-name.git'
            }
        }

        stage('Set Up Python Virtual Environment') {
            steps {
                sh 'python3 -m venv $VENV'
                sh './$VENV/bin/pip install --upgrade pip'
                // You can use requirements.txt or list them here:
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
