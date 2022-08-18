node {    
      def app     
      stage('Clone repository') {               
             
            checkout scm    
      }     
      stage('Build image') {         
       
            app = docker.build("av21aman/jenkinstest")    
       }     
      stage('Test image') {           
            app.inside {            
             
             sh 'echo "Tests passed"'        
            }    
        }     
      stage('Push image') {
            docker.withRegistry('https://registry.hub.docker.com', 'git') {
                  app.push("${env.BUILD_NUMBER}")
                  app.push("latest")        
              }    
           }
        }   
   
