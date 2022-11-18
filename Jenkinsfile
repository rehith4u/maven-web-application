pipeline{
    agent any
    
    stages{
        
        stage('CheckoutCode'){
            steps{
                git credentialsId: 'Git_Credentials', url: 'https://github.com/rehith4u/maven-web-application.git
            }
        }
    
        stage('Build'){
            steps{
                sh "mvn clean package"
                 }
        }
        
   stage ('deploy-dev') {
      steps {
	     echo "deploy to PCF-dev stage is running"
		 sh '''
		 cf login -a https://api.cf.us10-001.hana.ondemand.com -u rehith4i@gmail.com -p oneplus6T@ -o 09615f5ftrial -s dev
	     
		 cf push -f manifest.yml

		 '''
	  }
   }

    }
}
