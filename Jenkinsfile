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

      stage('checkforfile') {
         steps {
            script{
               if(fileExists('steps.txt'))
               println ("file steps.txt is in the dir")
               else println ("file step.txt is not in the dir")
                  }
               }
            }

      stage('checkfortext')
         steps{
            script{
               def steps = new File('steps.txt')
               def lines = steps.readLines()

               lines.each {String line -> println line}
               println "#########################"
               String test = "step eight"

               if(lines.contain("step eight")){
                  println test " is not in the list"
               }
               else{
                  println test " is not in the list"
               }
            }
         }      
      }
   }
