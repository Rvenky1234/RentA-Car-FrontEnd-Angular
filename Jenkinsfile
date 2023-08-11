pipeline {
     agent any
     stages {
         stage('Clean Workspace') {
             steps {
                  deleteDir()                  
             }
         }
         stage('Clone Project') {
             steps {                  
                  checkout scm                  
             }
         }
         stage ('JDK_11') {
             tools {
            jdk 'java'
            }
             steps{
               sh '''
              java -version
              '''
            }
        }
       stage ('Install') {
         sh "npm install"
       }
       stage ('Test') {
         sh "npm run test-headless"
       }
       stage ('Build') {
         steps {
           echo "Starting Build"
           sh 'ng build'
         }
       }
     }
 }
