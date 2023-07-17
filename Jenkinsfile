pipeline{
    agent any
    
    environment{
        
        registry = "ramurajula/dockerhubrepo1"
        registryCredential = 'dockerhubkey'        
    }
    
    stages{
       stage('Building image') {
      steps{
        script {
          dockerImage = docker.build registry + ":$BUILD_NUMBER"
        }
      }
    }
       stage('Deploy Image') {
      steps{
         script {
            docker.withRegistry( '', registryCredential ) {
            dockerImage.push()
          }
        }
      }
    }
}
