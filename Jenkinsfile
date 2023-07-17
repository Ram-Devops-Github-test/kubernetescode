pipeline{
    agent any
    
    environment{
        
        registry = "ramurajula/dockerhubrepo1"
        registryCredential = 'dockerhubkey'        
    }
    
    stages{
        stage('Clone repository') { 
            steps { 
                script{
                checkout scm
                }
            }
        }

        stage('Build') { 
            steps { 
                script{
                 app = docker.build("underwater")
                }
            }
        }
      
      
}
}
