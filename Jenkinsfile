pipeline {
  agent any
  stages {
    stage('Install') {
      steps {
        sh 'npm install'
        sh 'npm build'
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
