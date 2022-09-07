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
      stage('Docker build image') {
      agent { label 'demo' }
            steps {
              withDockerRegistry([credentialsId:"docker-login",url:""]) {
              sh "printenv"
              sh "dokcer build -t shanarun83/numeric-app:""$BUILD_ID"" ."
              sh 'docker push shanarun83/numeric-app:""$BUILD_ID""'
              }
              
            }
        }  
    }
}
