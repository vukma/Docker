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
            withCredentials([usernamePassword( credentialsId: 'docker-hub-credentials', usernameVariable: 'USER', passwordVariable: 'PASSWORD')]) 
                def registry_url = "https://hub.docker.com/repository/docker/vukma/docker-repo/"
                bat "docker login -u $USER -p $PASSWORD ${registry_url}"
                docker.withRegistry("http://${vukma/docker-repo}", "docker-hub-credentials") 
                     // Push your image now
                     bat "docker push vukma/docker-repo:latest1"
                    }
                }
            }
        }
