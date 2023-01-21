pipeline {
    agent {
       node {
         label "valaxy"
      }
    }
    environment {
        PATH = "/opt/maven/bin:$PATH"
    }
    stages {
        stage('Build') {
            steps {
                dir('app'){
                echo '<--------------- Building started --------------->'
                sh 'printenv'
                sh 'mvn clean install'
                echo '<------------- Build completed --------------->'
            }
            }
        }

  stage ("Sonar Analysis") {
            environment {
               scannerHome = tool 'Valaxy-SonarScanner'  //scanner name configured for slave 
            }
            steps {
                echo '<--------------- Sonar Analysis started  --------------->'
                withSonarQubeEnv('Valaxy-SonarQube') {    
                    //sonarqube server name in master
                    sh "${scannerHome}/bin/sonar-scanner"
                }    
                echo '<--------------- Sonar Analysis stopped  --------------->'
            }   
        }
    }
}
