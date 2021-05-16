node {
      def app    
      stage ('Checkout the code')
      {
        checkout scm 
      }
      stage('Build image') 
      {  
        app = docker.build("carlosagonzalez246/dockerjenkinsassessment")    
      }
      stage('Push image') 
      {
        docker.withRegistry('https://registry.hub.docker.com', '0215444e-da73-405b-a5de-9d6c02b56221') 
      {            
        app.push("${env.BUILD_NUMBER}")            
        app.push("latest")        
      }    
     }
  }
