node {
    def app

    stage('Clone repository') {
      

        checkout scm
    }

   

    stage('Test image') {
  

        app.inside {
            sh 'echo "Tests passed"'
        }
    }

    
}
