pipeline {
    agent {label 'devopsnew'} 
    stages {
        stage('My Build') { 
            steps {
              sh 'mvn package'
              sh 'pwd'
              sh 'ssh -o StrictHostKeyChecking=no'
              sh 'sudo scp -iR /home/newdevops/workspace/my fourth pipeline/target/hello-world-war-1.0.0.war ubuntu@172.31.13.135:/opt/tomcat/webapps/'
            }
        }
        stage('My deploy') { 
        agent {label 'slave_node12'}
            steps {
              sh 'sudo sh /opt/tomcat/bin/shutdown.sh'
              sh 'sleep 2'
              sh 'sudo sh /opt/tomcat/bin/startup.sh'
            }
        }
    }
}
