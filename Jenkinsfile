pipeline {
    agent none
    tools{
         maven '3.6.3'
    }
    stages {
        stage('Testing stage') {
            agent any
            steps {
                sh 'mvn test'
            }
        }
    }
}
