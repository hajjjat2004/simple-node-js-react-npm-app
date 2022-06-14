pipeline {
    agent {
        docker {
            image 'node:latest'
            args '-p 3000:3000'
        }
    }
    
    stages {
        stage('Checkout Source') {
            steps {
               git branch: 'master', credentialsId: 'tokenjenkins', url: 'https://github.com/hajjjat2004/simple-node-js-react-npm-app.git'
           }
        }
        
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        
       
    }
}
