pipeline {
  agent {
    label 'linux'
   }
	
stages {      
        stage('Build maven ') {
            steps { 
                    sh 'pwd'      
                    sh 'mvn  clean install package'
            }
        }
        
        stage('Copy Artifact') {
           steps { 
                   sh 'pwd'
		   sh 'cp -r target/*.jar docker'
           }
        }
         
        stage('Build docker image') {
           steps {
               script {         
                 def customImage = docker.build('saivikas/kubernetes', "./docker")
                 docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
                 customImage.push("${env.BUILD_NUMBER}")
                 }                     
           }
        }
	  }
    }

 /* stages{  
        stage('set Env') {
            steps { 
                sh 'pwd'
		sh 'mvn --version'

                
            }
        }
         stage('maven build') {
           steps {
		   
            sh 'mvn  clean install package'
            
			}
        }
    }
}
*/
