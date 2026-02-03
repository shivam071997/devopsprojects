pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/shivam071997/l2-devops-mini.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t l2-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker rm -f l2-app || true
                docker run -d -p 8080:8080 --name l2-app l2-app
                '''
            }
        }
    }
}
