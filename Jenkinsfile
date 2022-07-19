#!groovy

pipeline {
   agent any
   stages {
                     
      stage('hello') {
         steps {
            println ("hello world")
             }
           }
      
      stage('check list of files and working dir') {
         steps {
            script {
               sh "ls -la"
               sh "pwd"
                   } 
                }
              }
       
      stage('readfile') {
         steps {
            script {
               def data = readFile(file: 'steps.txt')
               println(data)         
                        }
                    }
               }           
            }
         }
