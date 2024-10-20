pipeline {
    agent any
    stages {
        stage("Get Project Code") {
            steps {
                git url: 'https://github.com/AymenXD/Springboot-App-with-Mongo.git', branch: 'main'
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
        stage('Docker Login') {
            steps {
                sh 'docker login -u aymenxd -p Aymounaa'
            }
        }
        stage("Push Docker Image to Docker Hub") {
            steps {
                script {
                    echo "Pushing Image to Docker Hub ..."
                    sh "docker tag spring-mongo aymenxd/spring-mongo:latest"
                    sh "docker push aymenxd/spring-mongo:latest"
                }
            }
        }
    }
}
