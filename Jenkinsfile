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
               sh 'npm install --save express'
               sh 'npm install --global yarn'
            }
    }
    
    stage('Build the project') {
      steps { 
        sh 'npm run build'
      }
    }
   }
  }