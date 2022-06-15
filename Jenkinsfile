pipeline {
     environment {
       dockerimagename = "hajjjat2004/nodetest"
       dockerImage = ""
     }
    agent any
    
    stages {
        stage('Checkout Source') {
            steps {
               git branch: 'master', credentialsId: 'tokenjenkins', url: 'https://github.com/hajjjat2004/simple-node-js-react-npm-app.git'
            }
         }
        stage('Build image') {
          steps{
            script {
              dockerImage = docker.build dockerimagename
            }
          }
        }
        
        stage('Pushing Image') {
           environment {
               registryCredential = 'dockerhublogin'
           }
           steps{
             script {
                docker.withRegistry( 'https://registry.hub.docker.com', registryCredential ) {
                dockerImage.push("latest")
                }
             }
          }
        }
        
        
         
    }
}
