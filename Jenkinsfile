#!groovy

pipeline {
   agent any
   stages {
                     
      stage('hello world') {
         steps {
            println ("hello world")
             }
           }
      
      stage('check list of files and the working dir') {
         steps {
            script {
               sh "ls -la"
               sh "pwd"
                   } 
                }
              }
       
      stage('read and echo the content of steps.txt file') {
         steps {
            script {
               def data = readFile(file: 'steps.txt')
               println(data)         
                        }
                    }
               }     

      stage('check if file steps.txt is in the working dir') {
         steps {
            script {
               if(fileExists('steps.txt'))
               println ("file steps.txt is in the dir")
               else println ("file step.txt is not in the dir")
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
   }
}
