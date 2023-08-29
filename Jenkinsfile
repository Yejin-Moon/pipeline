pipeline {
    agent any

    stages {
	stage('Chekcout') {
            steps {
                git branch: 'main',
		url: https://github.com/Yejin-Moon/source-maven-java-spring-hello-webapp.git
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
	stage('Deploy') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://192.168.56.11:8080')], contextPath: null, war: 'target/hello-world.war'
            }
        }

    }
}
