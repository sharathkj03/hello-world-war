pipeline {
    agent {label 'slave_node12'} 
    stages {
        stage('My Build') { 
            steps {
              sh 'mvn package'
              sh 'pwd'
              sh 'sudo scp -R /home/sharath/workspace/my fourth pipeline/target/hello-world-war-1.0.0.war ubuntu@172.31.5.38:/opt/tomcat/webapps/'
            }
        }
        stage('My deploy') { 
        agent {label 'node_snoofy'}
            steps {
              sh 'sudo sh /opt/tomcat/bin/shutdown.sh'
              sh 'sleep 2'
              sh 'sudo sh /opt/tomcat/bin/startup.sh'
            }
        }
    }
}
