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
            def readfile = readFile(file: 'steps.txt')
            readfile.split('\n').each{ line ->
               println(line)
              }
            } 
          }
        }
