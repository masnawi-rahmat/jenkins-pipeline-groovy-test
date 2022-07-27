#!groovy

pipeline {
   agent any
   stages {
                     
      stage('echo start of pipeline') {
         steps {
            script {
               println ("start of pipeline")
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
               def steps = readFile(file: "steps.txt") //&& 'step01.txt')
               steps.split('\n').each{ line ->
               println "test ${line}"
                  }
               } 
            }
         } 

      /*stage('read steps01.txt file and echo its content line-by-line') {
         steps {
            script {
               def steps01 = readFile(file: "steps01.txt")
               def newsteps = sh (script: "cat "+line+ " >> newsteps.txt")
               steps01.split('\n').each{ line ->
               println (newsteps)
                  }
               }
            }
         }*/
      
      /*stage('cat newsteps.txt') {
         steps {
           script {
               sh "cat newsteps.txt"
                 }
              }
           }*/
      
      stage('load path01.groovy from dir and execute code script') {
         steps {
            script {
               code = load 'path01.groovy'
                  }     
               }
            }

      stage('write file path02.groovy, confirm and cat created file') {
         steps {
            script {
               writeFile file: 'path02.groovy', text: 'def script02 = "process code 02"\nprintln (script02)\nreturn'
               sh 'ls -l path02.groovy'
               sh 'cat path02.groovy'  
                  }
               }
            }

      stage('read and find a string in a file and echo line containing string') {
         steps {
            script {
            def result = sh(returnStdout: true, script: "cat steps.txt | grep eight")
            println (result)
                  }
               }
            }

      stage('echo end of pipeline') {
         steps {
            script {
               println ("end of pipeline")
                  } 
               }
            }
         }
      }
