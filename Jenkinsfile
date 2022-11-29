pipeline {
    agent {label 'slave_node12'} 
    stages {
        stage('My Build') { 
            steps {
              sh 'mvn package'
            }
        }
        stage('My deploy') { 
        agent {label 'devopsnew'}
            steps {
              sh 'sudo cp -R target/hello-world-war-1.0.0.war /opt/apache-tomcat-10.0.27/webapps/'
              sh 'sudo sh /opt/apache-tomcat-10.0.27/bin/shutdown.sh'
              sh 'sleep 2'
              sh 'sudo sh /opt/apache-tomcat-10.0.27/bin/startup.sh'
            }
        }
    }
}
