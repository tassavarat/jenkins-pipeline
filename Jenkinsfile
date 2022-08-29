pipeline {
    agent any

    stages {
        stage("Build") {
            steps {
                script {
                    def nginx_image = docker.build("nginx_image:${env.BUILD_ID}", "./nginx")
                }
            }
        }
        stage("Deploy") {
            steps {
                sh "docker run -d -p 8000:80 --restart=on-failure --name nginx nginx_image:${env.BUILD_ID}"
            }
        }
    }
}
