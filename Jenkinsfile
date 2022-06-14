pipeline {
    agent any
      
    
    stages {
        stage('Checkout Source') {
            steps {
               git branch: 'master', credentialsId: 'tokenjenkins', url: 'https://github.com/hajjjat2004/simple-node-js-react-npm-app.git'
           }
        }
        
        stage('Build docker-compose') {
            steps {
                sh 'docker compose up -d --no-color --wait'
                sh 'docker ps -a'
            }
        }
        
       
    }
}
