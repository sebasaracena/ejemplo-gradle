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
        
    


        
    }
}
