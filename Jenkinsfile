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
               sh ''' 
               ls
               pwd
               '''
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

      stage('1 read steps.txt file and echo its content line-by-line into a new newsteps.txt file') {
         steps {
            script {
               def steps = readFile(file: "steps.txt")
               steps.split('\n').each{ line ->
               //println(line)
               if(line.equals("step three")){
                  line = "step three new"
               }else{
                  line = line
                        }
               println(line)      
                     }
                  } 
               }
            }    
         
      stage('2 read steps.txt file and echo its content line-by-line into a new newsteps.txt file') {
         steps {
            script {
               def steps = readFile(file: "steps.txt")
               steps.split('\n').each{ line ->
               sh "echo ${line} >> newsteps.txt"
                  }
               } 
            }
         }

      stage('cat newsteps.txt') {
         steps {
            script {
               sh "cat newsteps.txt"
            }
         }
      }

      stage('read steps01.txt file and echo and append its content line-by-line into newsteps.txt file') {
         steps {
            script {
               def steps01 = readFile(file: "steps01.txt")
               steps01.split('\n').each{ line01 ->
               sh "echo ${line01} >> newsteps.txt"
               }
            }
         }
      }
      
      stage('cat newsteps.txt again and remove same file') {
         steps {
           script {
               sh '''
               cat newsteps.txt
               rm newsteps.txt
               '''
            }
         }
      }
      
      stage('load path01.groovy from dir and execute code script') {
         steps {
            script {
               code = load 'path01.groovy'
                  }     
               }
            }

      stage('if file path01.groovy exists; write, comfirm and cat file path02.groovy; else write file pathnotfound.groovy') {
         steps {
            script {
               if(fileExists('path01.groovy')) {
               println ("file path01.groovy found")
               writeFile file: 'path02.groovy', text: 'def script02 = "process code 02"\nprintln (script02)\nreturn'
               sh '''
               ls -l path02.groovy
               cat path02.groovy
               ls
               rm path02.groovy
               ls
               '''
               }
               else {
                  println ("file path01.groovy is not found and writing file pathnotfound.groovy")
                  writeFile file: 'pathnotfound.groovy', text: 'def script03 = "process code 03"\nprintln (script03)\nreturn'
                  sh '''
                  ls -l pathnotfound.groovy
                  cat pathnotfound.groovy
                  ls
                  '''
                    }
                }
             }

          }

      stage('read and find a string in file steps.txt and echo line containing string') {
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
      
   post {
      always {
         //deleteDir()
         echo "Cleaning Up"
         }
   
      success {
         echo "Successful Deployment"
         }

      failure {
         echo "Failed Deployment"
         }

      unstable {
         echo "Unstable Deployment"
         }   
      }
   }