import jenkins.model.*
pipeline {
   agent any

   stages {
     stage() {
      steps {
        ansiColor('x-term') {
          script {
            dir("maven-1") {
              docker.withRegistry('https://hub.docker.com', 'demo') {
                docker.image("magalam87/sonar-scanner:v1").inside(){
                withSonrQubeEnv('sonarqube'){
                  sh """
                      sonar-scanner -Dproject.setting=./sonar-project.properties
                      """;
                }
                }
              }
            }
          }
        }
      }
     }
	      }
   }
