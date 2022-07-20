#!groovy

pipeline {
   agent any
   stages {
                     
      stage('echo start of pipelie') {
         steps {
            script {
               pintln ("start of pipelne")
                  }
               }
            }
                     
      stage('check list of files and the present working dir') {
         steps {
            script {
               sh "ls -la"
               sh "pwd"
                  } 
               }
            }

      stage('check if file steps.txt is in the working dir and echo result accordingly') {
         steps {
            script {
               if(fileExists('steps.txt'))
               println ("file steps.txt is in the dir")
               else println ("file step.txt is not in the dir")
                  }
               }
            }
       
      stage('read and echo the content of steps.txt file') {
         steps {
            script {
               def steps = readFile(file: 'steps.txt')
               println (steps)         
                  }
               }
            }     

      stage('read steps.txt file and echo its content line-by-line') {
         steps {
            script {
               def steps = readFile(file: 'steps.txt')
               steps.split('\n').each{ line ->
               println (line)
                  }
               }
            }
         } 

      stage('load path01.groovy script from dir') {
         steps {
            script {
               code = load 'path01.groovy'
                  }     
               }
            }

      stage('echo end of pipeline') {
        steps {
           script {
            println ("end of pipeline')
                  } 
               }
            }
         }
      }
   


