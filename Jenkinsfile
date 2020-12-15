pipeline {
    agent any

    stages {
        stage('compile') {
            steps {
                
                sh 'gradle clean build'
                
                
            }
        }
      
     
        stage('run jar') {
            steps {
              
                 sh 'JENKINS_NODE_COOKIE=dontKillMe nohup bash gradle bootRun'
               
                
            } 
        }
        
         stage('SonarQube analysis') {
             steps{
    def scannerHome = tool 'sonar-scanner';
    withSonarQubeEnv('SonarQube') { // If you have configured more than one global server connection, you can specify its name
      sh "${scannerHome}/bin/sonar-scanner"
    }
             }            
  }


        
    }
}
