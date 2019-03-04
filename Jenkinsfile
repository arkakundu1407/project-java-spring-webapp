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
    stage ('upload Artifactory') {
      steps {
      sh 'curl -X PUT -u admin:password -T target/azurehome.war "http://13.71.122.102:8081/artifactory/example-repo-local/azurehome.war"'
       }
    }
     
     
      stage('Deploy') {
          steps {
                  
                    sh 'cp /var/lib/jenkins/workspace/test_springboot_pipeline_project/target/azurehome.war /opt/tomcat/webapps/'
                }
       }
        
    }
  }
