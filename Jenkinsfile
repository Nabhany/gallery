pipeline {
    
  tools{
    nodejs 'NodeJs'
   }
   
  agent any
  
  stages {
      
    stage('clone repository') {
      steps { 
        git 'https://github.com/Nabhany/gallery.git'
      }
    }
    
   stage('Install Dependencies') {
       steps {
               sh 'npm install'
            }
    }
    
    stage('Testing Phase') {
      steps { 
        sh 'npm run test'
      }
    }

     stage('Slack send message'){
            steps{
        
                slackSend message: ''
                slackSend message: "Running JK Build Id: ${env.BUILD_ID} on ${env.JENKINS_URL}"
            }
        }
   }
  }