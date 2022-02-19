pipeline {
  agent any
  tools {
    maven 'maven-3.6.3' 
  }
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage ('Deploy') {
      steps {
        script {
           deploy adapters: [tomcat9(credentialsId: 'tomcat_credential', path: '', url: 'http://54.241.155.192:8090/')], contextPath: '/karnika', war: 'target/REST-assured_Cucumber-0.0.1-SNAPSHOT.jar' 
        }
      }
    }
  }
}
