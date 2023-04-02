pipeline {
  agent any
  tools {
    maven '3.6.3'
  }
  stages {
    stage ('Building phase') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage ('Testing Phase') {
      steps {
      sh 'mvn test' 
        }
      }
    stage ('Deploying phase') {
      steps {
        script {
          deploy adapters: [tomcat9(credentialsId: 'credentialofTomcat', url: 'http://13.53.235.32:8080')], contextPath: null, onFailure: false, war: 'target/*.war' 
        }
      }
    }
  }
  post{
        success{
            mail to: "officialsaurabhsahu@gmail.com",
            subject: "Build is completed Succesfully",
            body: "build successfully"
        }
    failure{
      mail to: "officialsaurabhsahu@gmail.com",
            subject: "Build is not Completed",
            body: "failed"
    }
  }
}
