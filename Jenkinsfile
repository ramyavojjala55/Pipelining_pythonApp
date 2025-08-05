pipeline {
    agent any

    environment {
        VENV = "venv"
    }

    stages {
        stage('Clone GitHub Repo') {
            steps {
                git branch: 'main', credentialsId: 'github-https', url: 'https://github.com/ramyavojjala55/Pipelining_pythonApp.git'
            }
        }

        stage('Set Up Python Virtual Environment') {
            steps {
                // Use py to call Python if that's how it's registered
                bat 'bat '"bat '"C:\\Users\\YourUsername\\AppData\\Local\\Programs\\Python\\Python311\\python.exe" -m venv venv'
                bat '.\\venv\\Scripts\\pip install --upgrade pip'
                bat '.\\venv\\Scripts\\pip install flask pandas numpy tensorflow'
            }
        }

        stage('Run Flask App') {
            steps {
                bat '.\\venv\\Scripts\\python app.py'
            }
        }
    }
}
