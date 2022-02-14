pipeline {
  agent any
  tools {
    maven 'maven-3.5.2' 
  }
  stages {
    stage ('Build') {
      steps {
        bat 'mvn clean package'
      }
    }
  }
}
