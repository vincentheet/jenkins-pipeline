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
      }
    }
    stage('Step 2') {
      steps {
        echo 'Hello World'
      }
    }
  }
}