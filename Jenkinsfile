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
	    agent { label 'node-1' }
         steps{
		    sh 'mvn clean install'
            echo "Build is successfull"		 
		}  
	}
	   stage('Deploy war file to tomcat'){
	    agent { label 'node-1' }
		 steps{
		    sh 'sudo cp /opt/jenkins/workspace/Java-Project/target/*.war /opt/apache-tomcat-9.0.65/webapps'
	        echo "Deploy is successfull"   
		}
    }
	    stage('Testing'){
		 agent { label 'node-1'}
          steps{
		    echo "Test is successfull"  
		}
	} 
  }
}
