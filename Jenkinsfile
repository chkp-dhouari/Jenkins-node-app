pipeline {
   
        
      agent {

          docker { image 'sourceguard/sourceguard-cli:latest' }
          

          }
    
     
     environment {
         
              SG_CLIENT_ID = '5bdd3443-3919-4acc-8212-ed140185bc0d'
              SG_SECRET_KEY = '15c8074c194b4eb8988cfe010309ff78'
              
              
             
            }
   
   stages{
      
        stage('convert docker image to .tar') {
           
           agent {

             docker { image 'sourceguard/sourceguard-cli:latest' }
          
              }
           
           steps {
             
             sh 'docker save f5devcentral/f5-demo-app -o f5.tar'
           
             }
  
          }
         
       
         stage('SourceGuard Imnage Scan') {
        
            steps {

                sh '/sourceguard-cli --src ./'

               }
          }
       
        
    }

}
