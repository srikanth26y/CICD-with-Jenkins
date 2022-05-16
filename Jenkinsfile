pipeline {
	
	environment {
		
		registry = "srikanth26y/webapp"
		
		registryCredential = 'docker-creds'
		
		dockerImages = ''

		}

	agent any

	stages {

		stage('Cloning Git'){

			steps{
			
				git  'https://github.com/srikanth26y/nginx-demo.git'

			}
		}
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
    
		stage('Remove Unused docker image') {

			steps{
       
				sh "docker rmi $registry:$BUILD_NUMBER"
     
			}
   
		}


	}
	
}
