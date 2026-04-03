pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/mdmuzamilali/portfolio-devops.git'
            }
        }

        stage('Build Docker') {
            steps {
                sh 'docker build -t portfolio .'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker stop portfolio || true'
                sh 'docker rm portfolio || true'
                sh 'docker run -d -p 80:80 --name portfolio portfolio'
            }
        }
    }
}
