import jenkins.model.*
pipeline {
  agent any   	
   stages {     

	  stage('SonarQubeScan') {
  		steps {
   		 ansiColor('xterm') {     		 
     		 script {
       		    dir("maven-1"){
                      sh '''
				   sonar-scanner -Dproject.settings=./sonar-project.properties
				  '''
        	    }
			  timeout(time: 1, unit: 'HOURS') {
         	  waitForQualityGate abortPipeline: false
        	}
		    }
		}
		}
		}		   
		  

}    		   

    
}
