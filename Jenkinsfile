pipeline 
 {
           agent {label 'main'}
  stages {
   
           stage('checkout')
     		  {
                 steps {
                          echo "----Now I will try to dpeloy Lunar system----"  
                       }
              }
          stage('build')
         	  {
      
                   environment {
                                JOB_NAME = "${env.JOB_NAME}"
                               }
                   steps  {
                                timestamps() 
				                     {
										sh "pwd"
										sh "whoami"
										echo "current job name : Lunar system"

										pwsh """ kubectl  apply -f ./jenkins/blob/main/mydeploy.yaml """ 
                                               
                                        pwsh """ kubectl  apply -f ./jenkins/blob/main/myservice.yaml """
              
                                     }
                          }           
              }
         }

	post {
		failure {
					echo "Execution failed unfortunately"							
				}
		}      
 }
