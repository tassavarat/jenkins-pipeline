pipeline {
    agent {
        dockerfile {
            dir "nginx"
        }
    }
    stages {
        stage("Build") {
            steps {
		def nginx = docker.build("nginx-test:${env.BUILD_ID}", "./nginx")
            }
        }
	stage("Deploy") {
	    steps {
	        sh "docker run -d -p 8000:80 --restart=on-failure --name nginx nginx-test:v1"
	    }
	}
    }
}
