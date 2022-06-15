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
         stage('start container') {
              steps{
                   script { 
                        sh 'docker run -it --name apptest -d -p 3000:3000 hajjjat2004/nodetest'
                        
                   }
              
              }
         
         }
        
         
    }
}
