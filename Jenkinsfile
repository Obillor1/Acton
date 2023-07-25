pipeline {
  agent any 
  stages {
    stage ('Docker build') {
      step {
      sh "docker build -t obillor1/newrepo:v1 ."
      }
    }
     stage('Login and Push Image') {
       steps {
        withDockerRegistry([ credentialsId: "obillor1", url: "" ]) {
        sh "docker push obillor1/newrepo:v1"
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


