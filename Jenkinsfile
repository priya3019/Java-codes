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
		    sh 'cp -r /opt/jenkins/workspace/build/target/hello-world-war-1.0.0.war /home/ec2-user/tomcat/apache-tomcat-9.0.65/webapps'
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
