pipeline{
    agent any
    
    environment{
        
        registry = "ramurajula/dockerhubrepo1"
        registryCredential = 'dockerhubkey'        
    }
     stage('Initialize'){
        def dockerHome = tool 'myDocker'
        env.PATH = "${dockerHome}/bin:${env.PATH}"
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
                    echo 'Starting to build docker image'
                    
                 def app = docker.build("my-image:${env.BUILD_ID}")
                }
            }
        }
      
      
}
}
