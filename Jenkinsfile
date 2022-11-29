pipeline {
    agent {label 'devopsnew'} 
    stages {
        stage('My Build') { 
            steps {
              sh 'mvn package'
              sh 'pwd'
            }
        }
        stage('My deploy') { 
        agent {label 'slave_node12'}
            steps {
              sh 'sudo scp -R /home/newdevops/workspace/my fourth pipeline/target/hello-world-war-1.0.0.war root@172.31.13.135/opt/tomcat/webapps/'
              sh 'sudo sh /opt/tomcat/bin/shutdown.sh'
              sh 'sleep 2'
              sh 'sudo sh /opt/tomcat/bin/startup.sh'
            }
        }
    }
}
