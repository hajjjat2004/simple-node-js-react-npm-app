pipeline {
     agent any
     stages {
        
        stage('Checkout Source') {
           steps {
              git branch: 'main', credentialsId: 'tokenjenkins', url: 'https://github.com/hajjjat2004/simple-node-js-react-npm-app.git'
            }
        } 
         
         
        stage("Build") {
            steps {
                sh "sudo npm install"
                sh "sudo npm run build"
            }
        }
        stage("Deploy") {
            steps {
                sh "sudo rm -rf /var/www/jenkins-react-app"
                sh "sudo cp -r ${WORKSPACE}/build/ /var/www/jenkins-react-app/"
            }
        }
    }
}
