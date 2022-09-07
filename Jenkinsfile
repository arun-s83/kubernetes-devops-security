pipeline {
  agent any

  stages {
      stage('Build Artifact') {
      agent { label 'demo' }
            steps {
              sh "mvn clean package -DskipTests=true"
              archive 'target/*.jar' //so that they can be downloaded later
            }
        }   
    }
}
