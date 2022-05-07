pipeline {
    agent any
    tools {
        maven "M3"
    }
    stages {
        stage('Build') {
            steps {
                git 'https://github.com/ashishprajapati936/sample-may.git'
                sh "mvn clean install"
            }
            post {
                success {
                    archiveArtifacts 'target/*.war'
                }
            }
        }
		stage('Deploy') {
            steps {
                sh "cp target/boa-may.war ~/tomcat/webapps/ashish.war"
            }
        }

    }
}