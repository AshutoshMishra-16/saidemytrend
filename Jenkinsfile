pipeline {
    agent any
    environment {
       PATH = "/opt/maven/bin:$PATH"
    }
    stages {
       stage('build') {
          steps {
              sh 'mvn clean deploy'
          }
      }
      stage('SonarQube analysis') {
          environment = tool 'ashutosh-sonarqube-scanner'
          }
         
          steps {
              withSonaqQubeEnv('ashutosh-sonarqube-server') {

                 sh "${scannerHome}/bin/sonar-scanner"
              }
          }
      }
   }

