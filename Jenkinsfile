pipeline {
    agent {label 'newdevops'} 
    stages {
        stage('My Build') { 
            steps {
              sh 'mvn package'
              sh 'pwd'
              sh 'whoami'
              sh 'scp -R /home/newdevops/workspace/'build and deploy'/target/hello-world-war-1.0.0.war ubuntu@172.31.5.38:/opt/tomcat/webapps/'
            }
        }
        stage('My deploy') { 
        agent {label 'newagent'}
            steps {
              sh 'sudo sh /opt/tomcat/bin/shutdown.sh'
              sh 'sleep 2'
              sh 'sudo sh /opt/tomcat/bin/startup.sh'
            }
        }
    }
}
