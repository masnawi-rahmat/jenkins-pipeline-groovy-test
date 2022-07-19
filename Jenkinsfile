//#!groovy

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
                   sh "head -1 sometext.txt" 
               }
           }
       }
