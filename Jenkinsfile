pipeline {
  agent any; 
  environment {
    NAME = 'sujay'
  }
  parameters {
  string defaultValue: '1234', description: 'Practicing the assignment', name: 'sujay', trim: true
  } 
  stages {
        stage ('BUILD') {
  steps {
            git(
            credentialsId: 'f086fa91-c575-4c18-897c-2d5c3b69cffc', url: 'https://github.com/sujayprabhu/assignment1pract.git'
            )   
         sh '''
            mvn clean package
            '''
         }
       }   
    stage ('TEST PARALLEL') {
      parallel {
        stage ('TEST ON CHROME') {
           steps {
             echo "this is test stage on chrome"
             sh "sleep 5"
           }
        }
         stage ('TEST on firefox') {
           steps {
             echo "this is test stage on firefox"
             sh "sleep 5"
           }
        }  
      } 
    }    
     
    stage ('DEPLOY') {
      steps {
        echo "this is deploy stage "
        sh "sleep 5"
      }
    }
  }
}
