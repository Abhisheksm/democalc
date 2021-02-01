pipeline {

  agent any
  stages {
    stage('Compile') {
      steps{
        sh 'mvn clean compile'
      }
    }
    
    stage('Unit Test') {
      steps{
        sh 'mvn clean test'
      }
    }

    stage('Package') {
      steps{
        sh 'mvn clean install'
      }
    }
   stage('ContDelivery'){
       steps{
             deploy adapters: [tomcat9(credentialsId: 'tomcat', pth: '', url: http://192.168.33.10:9090/')]. contextPath: null, war: 'target/calculator.war'
       }
     }
  }
}
