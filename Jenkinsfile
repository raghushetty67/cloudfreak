pipeline {
  agent any
  
  tools {
  maven 'maven3'
  jdk 'jdk8'
  }

  stages{  
        stage('set Env') {
            steps { 
                sh 'pwd'
                sh label: '', script: 'export JAVA_HOME=/home/ubuntu/jdk1.8.0_241'
                sh label: '', script: 'export PATH=$JAVA_HOME/bin:$PATH'
                sh label: '', script: 'export M2_HOME=/home/ubuntu/apache-maven-3.6.3'
                sh label: '', script: 'export PATH=$M2_HOME/bin:$PATH'
                sh label: '', script: 'export PATH'
                
            }
        }
         stage('maven build') {
           steps {
		   
            sh 'mvn  clean install package'
            
			}
        }
    }
}
