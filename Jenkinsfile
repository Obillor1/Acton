pipeline {
  agent any 
  stages {
    stage ('Docker build') {
      steps {
      sh 'docker build -t obillor1/appsrt:${BUILD_ID} .'
      }
    }
    stage ('Get Environment variable') {
      steps {
        sh 'printenv'
      }
    }
     stage('Login and Push Image') {
       steps {
        withDockerRegistry([ credentialsId: "obillor1", url: "" ]) {
        sh "docker push obillor1/appsrt:${BUILD_ID}"
        }
       }
     }
    stage ('Remove unwanted Images'){
      steps {
        sh 'docker rmi -f $(docker images -q)'
      }
    }
  }
}


