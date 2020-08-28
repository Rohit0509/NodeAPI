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
           def scannerHome = tool 'sonarScanner';
		withSonarQubeEnv('sonar-1') { 
	sh 'echo "here ===>>>>> "'
               sh "${tool("sonarqube")}/bin/sonar-scanner \
               -Dsonar.projectKey=test-node-js \
               -Dsonar.sources=. \
               -Dsonar.css.node=. \
               -Dsonar.host.url=http://15.207.83.196:9000 \
               -Dsonar.login=9a3bac7bdf21ef068e37131712fcdd36085bb471"	
		
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
