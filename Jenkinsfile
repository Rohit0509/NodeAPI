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
           sh 'echo "ss"'
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
