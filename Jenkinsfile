pipeline{
    agent any
    
    environment{
        
        registry = "ramurajula/dockerhubrepo1"
        registryCredential = 'dockerhubkey'        
    }
     
    stages{
        
        stage('Initialize'){
            steps { 
                script{
            RUN curl -fsSLO https://get.docker.com/builds/Linux/x86_64/docker-17.04.0-ce.tgz \
  && tar xzvf docker-17.04.0-ce.tgz \
  && mv docker/docker /usr/local/bin \
  && rm -r docker docker-17.04.0-ce.tgz
                }
            }
    }
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
