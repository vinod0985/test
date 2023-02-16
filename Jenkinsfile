import jenkins.model.*
pipeline {
 agent any
  stages {
    stage('demo') {
      steps {
	     script{
           dir(maven-1) {
            withSonarQubeEnv('sonarqube') {
               sh """
                 		  ls -lrta			          
				              sonar-scanner -Dproject.settings=./sonar-project.properties
                  """
	          }
         }
         sleep(10)  
       		 timeout(time: 1, unit: 'HOURS') {
         	 waitForQualityGate abortPipeline: false
        	}
	         
	      }
        }
      }
    }
}
