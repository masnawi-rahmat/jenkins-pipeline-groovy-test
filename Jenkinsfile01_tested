#!groovy

pipeline {
   agent any
   stages {
       
      stage('clearspace') {
         steps {
            println ("clearing space now")
            cleanWs()
               }
            }
           
      stage('hello') {
         steps {
            println ("hello world")
             }
           }
      
      stage('ls') {
         steps {
            script {
               sh "ls -l"
                   } 
                }
              }
            }
         }
