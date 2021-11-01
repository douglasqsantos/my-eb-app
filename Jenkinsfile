// Powered by Infostretch 

timestamps {

node ('beanstalk') { 

	stage ('my-eb-app - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'douglasqsantos', url: 'https://github.com/douglasqsantos/my-eb-app']]]) 
	}
	stage ('my-eb-app - Build') {
 			// Shell build step
sh """ 
#env
# Initialize the elastic beanstalk app
eb init my-eb-app --platform python-3.8 --region us-east-2

# Select the development environment for deployment
eb use Myebapp-env

# Deploy the application
eb deploy

# Get the health and status information
eb health
eb status 
 """ 
	}
}
}