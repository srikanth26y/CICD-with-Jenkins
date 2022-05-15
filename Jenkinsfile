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

	}
}
