pipeline {
  agent any
  stages {
    stage('Install') {
      steps {
        sh 'npm install'
        sh 'npm build'
      }
    }
    
    stage('Sonarqube'){
      steps {
        sh 'echo "sonar qube scanning"'
        withSonarQubeEnv('sonar-6') {
          def scannerHome = tool 'sonarScanner';
          sh "${scannerHome}/bin/sonar-scanner"
        }
      }
    }
     
    stage('Test') {
      steps {
         sh 'npm test'
       }
    }  
    stage('Deploy') {
      steps {
         sh 'echo "Deploy"'
      }
    }
  }
}
