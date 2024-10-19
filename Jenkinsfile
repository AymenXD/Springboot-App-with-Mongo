pipeline {
    agent any
    stages {
        stage("Get Project Code") {
            steps {
                git url 'https://github.com/AymenXD/Springboot-App-with-Mongo.git'
            }
        }
        stage("Dockerize Project") {
            steps {
                script {
                    echo "Dockerizing App ..."
                    sh "docker build -t spring-mongo ."
                }
            }
        }
        stage("Push Docker Image to Docker Hub") {
            steps {
                script {
                    echo "Pushing Image to Docker Hub ..."
                    echo "push to hub"
                    sh "docker push spring-mongo"
                }
            }
        }
    }
}
