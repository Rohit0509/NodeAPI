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
        sh 'echo "Build"'
       }
    }  
    stage('Test') {
      steps {
        sh 'npm test'
      }
    }
  }
}
