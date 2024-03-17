node {
    stage ("Checkout CustomerServiceAPI"){
        git branch: 'main', url: ' https://github.com/foxwas/customerserviceAPI.git'
    }
    
    stage ("Maven Build - CustomerServiceAPI") {
	
        bat 'mvn install'

    }
    
    stage ("API Tests- CustomerServiceAPI") {
        bat  'mvn test'
    }
    
    stage('User Acceptance Test - CustomerServiceAPI') {
	
	  def response= input message: 'Is this build good to go?',
	   parameters: [choice(choices: 'Yes\nNo', 
	   description: '', name: 'Pass')]
	
	  if(response=="Yes") {

	    stage('Release- DataService') {
	     bat 'echo DataService is ready to release!'

	    }
	  }
    }
}