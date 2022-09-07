pipeline {
  agent any

  stages {
      stage('Build Artifact') {
      agent { label 'demo' }
            steps {
              sh "mvn clean package -DskipTests=true"
              archive 'target/*.jar' //File can be downloaded later
            }
        }   
      stage('Unit Test') {
      agent { label 'demo' }
            steps {
              sh "mvn test"
              
            }
        }  
      stage('Print the environment') {
      agent { label 'demo' }
            steps {
              sh "printenv"
              
            }
        }  
    }
}
