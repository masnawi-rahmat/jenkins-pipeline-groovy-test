#!groovy

pipeline {
   agent any
   stages {
       stage('write') {
           steps {
               script {
                   def date = new Date()
                   def data = "Hello World\nSecond line\n" + date
                   writeFile(file: 'zorg.txt', text: data)
                   sh "ls -l"
                   sh "cat zorg.txt"
                   //sh "head -1 sometext.txt" 
               }
           }
       }
       stage('read') {
           steps {
               script {
                   //def data = readFile(file: 'zorg.txt')
                   def data = readFile(file: 'steps.txt')
                   //data.split('\n') 
                   println(data)
                   //println(line)
               }
           }
       }
   }
}
