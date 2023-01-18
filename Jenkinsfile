pipeline {
    agent any

    stages {
        stage('Building') {
            steps {
                git clone 'https://github.com/veitham/JenkinsFlask.git'
            }
        }

        stage('Testing') {
            steps {
                sh 'pip install -r requirements.txt'
                sh 'pytest'
            }
        }

        stage('Deploying') {
            steps {
                sh 'docker build -t my-flask-app .'
                sh 'docker run -p 8080:8080 my-flask-app'
            }
        }
    }
}
