#!groovy
pipeline {
    agent any
   stages {     
    stage('Build') {
        steps {
	   sh 'rm -rf petclinic'
           sh 'git clone https://github.com/so008mo/petclinic.git'
	   sh 'cd petclinic'
	   sh 'mvn compile -Dimage=spring/petclinic:spring-k8s-1 \
	         com.google.cloud.tools:jib-maven-plugin:1.0.0:dockerBuild'
       }
     }
   }
 }
