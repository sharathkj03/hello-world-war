pipeline {
    agent {label 'slave_node12'} 
    stages {
        stage('My Build') { 
            steps {
              sh 'mvn package'
              sh 'pwd'
              sh 'scp -R /home/newdevops/workspace/build and deploy/hello-world-war-1.0.0.war ubuntu@172.31.5.38:/opt/tomcat/webapps/'
            }
        }
        stage('My deploy') { 
        agent {label 'devopsnew'}
            steps {
              sh 'sudo sh /opt/tomcat/bin/shutdown.sh'
              sh 'sleep 2'
              sh 'sudo sh /opt/tomcat/bin/startup.sh'
            }
        }
    }
}
