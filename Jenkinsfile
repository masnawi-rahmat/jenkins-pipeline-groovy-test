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
               sh "ls -l"
               def data = readFile(file: 'steps.txt')
               println(data)
                        } 
                    }
                }
             }
         }
