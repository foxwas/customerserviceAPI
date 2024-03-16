node {
    stage ("Checkout CustomerService"){
        git branch: 'main', url: ' https://github.com/foxwas/customerserviceAPI.git'
    }
    
    stage ("Maven Build - CustomerService") {
	
        bat 'mvn compile'

    }
    
    stage ("Package - CustomerService") {
        bat  'mvn package'
    }
    
    stage ("API Tests- CustomerService") {
        bat  'mvn test'
    }
    
    stage('User Acceptance Test - CustomerService') {
	
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