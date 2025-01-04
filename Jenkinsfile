pipelne {
	agent any
	environment {
	   MVN= "/usr/share/maven/bin"
        }
	options {
 	    timeout(time: 1, unit: 'HOURS')
	    retry(3)
        }
        triggers {
	    cron('0 * * * *')
        }
        stages {
           stage ('Git clone') {
              steps {
                  git url: 'https://github.com/Jenkins-Course/spring-petclinic.git', branch: 'main'
              }
            }
           stage ('Build the code') {
  	      steps {
                  sh script: "$MVN clean package"
              }
              
           }

         }
	post {
        success {
            echo "Success"
            }
        unsuccessful {
              echo "Failure"
              }
        }    
}

