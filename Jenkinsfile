pipeline {
  agent any
  
  tools {
  maven 'maven3'
  jdk 'jdk8'
  }

  stages{  
        stage('Build maven ') {
            steps { 
                sh 'pwd'      
                sh 'mvn  clean install package'
            }
        }
    }
}
