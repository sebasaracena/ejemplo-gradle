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
        
    

  stage('Sonar') {
        

               def scannerHome = tool 'sonar-scanner';
      steps{
    withSonarQubeEnv('SonarQube') { // If you have configured more than one global server connection, you can specify its name
      bat "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=ejemplo-gradle -Dsonar.java.binaries=build"

    
     }

           }
        }

        
    }
}
