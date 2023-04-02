pipeline {
  agent any
  tools {
    maven "3.6.3"
  }
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage ('Testing') {
      steps {
      sh 'mvn test' 
        }
      }
    stage ('Deploy') {
      steps {
        script {
          deploy adapters: [tomcat9(credentialsId: 'credentialTomcat', url: 'http://16.16.77.63:8090/')], contextPath: null, onFailure: false, war: 'target/*.war' 
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
