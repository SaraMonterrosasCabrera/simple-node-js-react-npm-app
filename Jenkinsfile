pipeline {
    agent {
        docker {
            image 'node:6-alpine' 
            args '-p 3000:3020' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }
        
        
       stage('Test') { 
            steps {
                sh './jenkins/scripts/test.sh' 
            }
        }
        
        stage('Deliver') { 
            steps {
                sh './jenkins/scripts/deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to Continue)'
                sh './jenkins/scripts/kill.sh'
            }
        }
        
        
    }
   
}
