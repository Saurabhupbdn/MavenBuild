pipeline {
  agent any
  tools {
    maven 'Maven 3.6.3'
  }
  stages {
    stage ('Build at production') {
      steps {
        echo 'build is completed'
      }
    }
  stage ('testing at production') {
      steps {
        sh 'mvn test'
      }
    }
  }
}
