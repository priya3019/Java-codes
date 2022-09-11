pipeline{
   agent none
   stages {
      stage('Git checkout'){
	    agent { label 'node-1' }
         steps{
		    git 'https://github.com/priya3019/Java-codes.git'
		    echo "Checkout is successfull"
		
	    }  		
	}
	   stage('Build'){
	    agent { label 'slave1' }
         steps{
		    sh 'mvn clean install'
            echo "Build is successfull"		 
		}  
	}
	   stage('Deploy war file to tomcat'){
	    agent { label 'slave1' }
		 steps{
		    sh '/opt/jenkins'
	        echo "Deploy is successfull"   
		}
    }
	    stage('Testing'){
		 agent { label 'slave1'}
          steps{
		    echo "Test is successfull"  
		}
	} 
  }
}
