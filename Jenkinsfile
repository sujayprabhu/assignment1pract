pipeline {
  agent any; 
  environment {
    NAME = 'sujay'
  }
  parameters {
  string defaultValue: '1234', description: 'Practicing the assignment', name: 'sujay', trim: true
    booleanParam description: 'this is a practice file', name: 'jenkin'
  choice choices: ['false or true'], description: 'this is a example', name: 'redhat'
  file 'd location'
  credentials credentialType: 'com.cloudbees.plugins.credentials.impl.UsernamePasswordCredentialsImpl', defaultValue: '', description: 'practice', name: 'mastercard', required: false
  } 
  stages {
        stage ('BUILD') {
  steps {
            git(
               'https://github.com/sujayprabhu/assignment1pract.git'
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
