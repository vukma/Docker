pipeline {
    agent any
    
    stages {
        stage('Git clone') {
            steps {
                git 'https://github.com/vukma/Docker.git'
            }
        }
        stage('Create Dockerimage') {
            steps {
                bat 'docker build -t vukma/docker-repo:latest1 .'
            }
        }
        stage('Push image') {
            steps {
            docker.withRegistry('https://hub.docker.com/repository/docker/vukma/docker-repo/', 'docker-hub-credentials') {
                bat "docker push vukma/docker-repo:latest1"
        }
    }
}
