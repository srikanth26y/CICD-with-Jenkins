pipeline {
	
	environment {
		
		registry = "srikanth26y/nginx-demo-project"
		
		registryCredential = 'docker-creds'
		
		dockerImages = ''

		}

	agent any

	stages {

		stage('Cloning Git'){

			steps{
			
				git  'https://github.com/srikanth26y/nginx-demo-project.git'

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
		
		stage('Remove Existing Container') {
      
			steps{
	 
				script {
			
					sh '''
					a="$(docker container ls --format="{{.ID}}\t{{.Ports}}" | grep "8000" | awk '{print $1}')"
					echo $a
					if [ -z "$a" ]
					then
					echo "do not delete"
					else
					docker rm -f $a
					fi
					'''
		
				}
      
			}

    
		}
		
		
		stage('Run Docker Image in Lab') {
			
			steps{

       
				script {

		     
					sh "docker run -d -p 8000:80 ${dockerImage.imageName()}"
       
				}

      
			}

	
		}
		
	}
	
}
    

	

