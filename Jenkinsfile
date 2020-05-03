pipeline {
  agent {
    label 'linux'
   }

  stages{  
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
