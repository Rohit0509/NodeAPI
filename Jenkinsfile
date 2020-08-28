pipeline {
  agent any
  stages {
    stage('Install') {
      steps {
        sh 'npm install'
        sh 'npm build'
      }
    }
    /*
    stage('Sonarqube'){
      steps {
        sh 'echo "sonar qube scanning"'
         script {
          withSonarQubeEnv('sonar-1') { 
              sh 'echo "here ===>>>>> "'
              sh "${tool('sonarScanner')}/bin/sonar-scanner \
              -Dsonar.projectKey=test-node-js \
              -Dsonar.sources=. \
              -Dsonar.css.node=. \
              -Dsonar.analysis.mode=. \
              -Dsonar.host.url=http://15.207.83.196:9000 \
              -Dsonar.login=9a3bac7bdf21ef068e37131712fcdd36085bb471"	
            }
        }
      }
    }
    */

    stage('Sonarqube') {
      steps {
          sh 'echo "here ==>>> "'
          withSonarQubeEnv('sonar-1') {
            sh 'echo "===>>>> INSIDE ===>>>> "'
            sh "${tool('SonarQube Scanner 4.4')}/bin/sonar-scanner"
          }
          timeout(time: 10, unit: 'MINUTES') {
            waitForQualityGate abortPipeline: true
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
