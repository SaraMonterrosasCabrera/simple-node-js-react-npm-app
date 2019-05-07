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
    }
 
    stages {
        stage('Test') { 
            steps {
                sh 'test.sh' 
            }
        }
    }    
    
    
    
}
