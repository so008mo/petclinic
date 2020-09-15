#!groovy
pipeline {
    agent none
   stages {     
    stage('Maven Install') {
      agent {         
       docker {          
         image 'maven:3.5.0'         
     }       
  }       
      steps {
       sh 'rm -rf petclinic'
       sh 'git clone https://github.com/so008mo/petclinic.git'
       sh 'cd petclinic'
       sh 'sudo ./mvnw spring-boot:run'
       }
       }
    stage('Docker build') {
      agent any
      steps {
        sh 'docker build -t arsenal14h/petclinic:latest .'
	}
     }
   }
 }
