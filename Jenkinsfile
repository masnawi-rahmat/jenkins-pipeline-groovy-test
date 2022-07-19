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
      
      stage('readfile') {
         steps {
            script {
               def readimage = readFile(file: 'steps.txt')
                   println(readimage)
                        } 
                    }
                }
             }
         }
              
