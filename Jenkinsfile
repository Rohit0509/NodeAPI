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
        script {
            def scannerHome = tool 'sonarqube';
           withSonarQubeEnv("sonar-1") {
               sh 'echo "here ===>>>>> "'
             }
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
