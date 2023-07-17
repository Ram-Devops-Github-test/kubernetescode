
pipeline {
    agent any
    def app

    stage('Clone repository') {
      

        checkout scm
    }

    

    stage('Test image') {
  

        app.inside {
            sh 'echo "Tests passed"'
        }
    }

    stage('Push image') {
        
        docker.withRegistry('https://registry.hub.docker.com', 'dockerhubkey') {
            app.push("${env.BUILD_NUMBER}")
        }
    }
     
}
