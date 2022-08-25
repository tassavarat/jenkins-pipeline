pipeline {
    agent {
        dockerfile {
            dir "nginx"
        }
    }
    stages {
        stage("Build") {
            steps {
                sh "docker build -t nginx-test:v1 nginx"
            }
        }
	stage("Deploy") {
	    steps {
	        sh "docker run -d -p 8080:80 --restart=on-failure --name nginx nginx-test:v1"
	    }
	}
    }
}
