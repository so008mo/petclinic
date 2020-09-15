#!/bin/env groovy

pipeline {
  agent none
  stages {
    stage('Build') {
      agent {
        docker {
          image 'maven:3.5.0'
        }
      }
      steps {
          sh 'mvn clean install -B'
      }
    }
    stage('Build container') {
      agent any
      steps {
            sh "docker build -t petclinic:latest ."
      }
    }
    stage('Docker Push') {
      agent any
      steps {
        withCredentials([usernamePassword(credentialsId: 'dockerHub', passwordVariable: 'dockerHubPassword', usernameVariable: 'dockerHubUser')]) {
	   sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPassword}"
	   sh 'docker push arsenal14h/petclinic:latest'
	   }
	   }
	   }
  }
}
