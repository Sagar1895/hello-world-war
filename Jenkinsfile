pipeline {
    agent { label 'java' }
    stages {
        stage('checkout') { 
            steps {
              sh "git clone https://github.com/Sagar1895/hello-world-war"
            }
        }
stage('build') { 
            steps {
              sh "mvn build"
            }
        } 
        stage('deploy'){
            steps {
                sh "cp /home/jenkins-slave/jenkins/workspace/pipe1/target/hello-world-war-1.0.0.war /opt/apache-tomcat-9.0.60/webapps"
            }
    }
    }
}
