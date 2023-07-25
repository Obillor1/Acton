pipeline {
  agent any 
  stages {
     stage('Build and Push Image') {
       steps {
        withDockerRegistry([ credentialsId: "obillor1", url: "" ]) {
        sh "docker build -t obillor1/newrepo:v1"
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





   // stage ('Docker Login') {
     // steps {
        withDockerRegistry([credentialsId: 'obillor1', url: ""]){
     // }
   // }
    //}
        
    //stage ('Build Image') {
     // steps {
       // sh 'docker build -t obillor1/newrepo:v1 .'
      //}
    //}
    //stage ('Publish Image') {
      //steps {
        //sh 'docker push obillor1/newrepo:v1'
      //}
    //}
