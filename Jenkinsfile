pipeline {
  agent any
  tools {
          maven 'maven3.6.0'
          jdk 'java1.8.0'
        }
  stages {
      stage('Build') {
          steps {
                  
                    sh "mvn -B -Dskiptests clean package"
                }
       }
     
     
      stage('Deploy') {
          steps {
                  
                    sh 'cp /var/lib/jenkins/workspace/test_pipeline_project/target/azurehome.war /opt/tomcat/webapps/'
                }
       }
        
    }
  }
