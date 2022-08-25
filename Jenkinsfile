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
	        sh "docker run -d -p 8000:80 --restart=on-failure --name nginx nginx-test:v1"
	    }
	}
    }
}
