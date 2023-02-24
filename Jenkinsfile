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
               sh 'npm install multer'
               sh 'npm install mongoose'
               sh 'npm install mongodb'
               sh 'npm install chai-http'
               sh 'npm install express'
               sh 'npm install ejs'
               sh 'npm install chai'
               sh 'npm install mocha'

            }
    }
    
    stage('Build the project') {
      steps { 
        sh 'npm run build'
      }
    }

   }

post {
        success {
        
        slackSend message: 'link to code is gallerymoringa.herokuapp.com'
        slackSend message: "Running JK Build Id: ${env.BUILD_ID} on ${env.JENKINS_URL}"

        }failure{
        
        slackSend message: 'Failed to build'
        slackSend message: "Running JK Build Id: ${env.BUILD_ID} on ${env.JENKINS_URL}"

        }
    }

  }