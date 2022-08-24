pipeline {
  agent any
  tools {
  maven 'maven'
  }
    stages {
           stage ('Build')  {
	    steps {
              dir('app'){
              sh "mvn package"
          }
        }
   }
  }
  }
