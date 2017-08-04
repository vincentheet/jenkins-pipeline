pipeline {
  agent {
    kubernetes {
      //cloud 'kubernetes-plugin-test'
      label 'mypod'
      containerTemplate {
        name 'maven'
        image 'maven:3.3.9-jdk-8-alpine'
        ttyEnabled true
        command 'cat'
      }
    }
  }
  stages {
    stage('Step 1: versions') {
      steps {
        sh 'mvn -version'
        sh 'java -version'
      }
    }
    stage('Step 2') {
      steps {
        echo 'Hello World'
      }
    }
    stage('Notify') {
      steps {
        hipchatSend credentialId: "hipchat-token" room: "ok-jenkins", message: "Build finished: ${env.JOB_NAME} ${env.BUILD_NUMBER}"
      }
    }
  }
}