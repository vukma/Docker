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
                bat 'docker build -t vukma/docker-repo:lts1 .'
            }
        }
        stage('Push') {
            steps {
                bat 'docker push vukma/docker-repo:lts1'
            }
        }
    }
}
