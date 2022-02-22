pipeline {
  agent any
  tools {
    maven 'maven3' 
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
           deploy adapters: [tomcat9(credentialsId: 'tomcat_credential', path: '', url: 'http://18.118.26.191:8090/')], contextPath: '/karnika', war: 'target/REST-assured_Cucumber-0.0.1-SNAPSHOT.jar' 
        }
      }
    }
  }
}
