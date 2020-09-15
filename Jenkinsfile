#!groovy
pipeline {
    agent any
   stages {     
    stage('Build') {
        steps {
	   sh 'rm -rf petclinic'
           sh 'git clone https://github.com/so008mo/petclinic.git'
	   sh 'cd petclinic'
	   sh './mvnw package'
	   sh 'java -jar target/*.jar'
       }
     }
   }
 }
