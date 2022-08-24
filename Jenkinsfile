pipeline {
  agent any
  tools {
  maven 'maven'
  }
stage ('Build')  {
	    steps {
        dir('app'){
            sh "mvn package"
          }
        }    
   }
  }
  }
