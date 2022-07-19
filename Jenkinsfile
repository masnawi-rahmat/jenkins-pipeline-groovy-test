#!groovy

pipeline{
  agent any
  stage('readfie') {
    steps {
      script {
        def data = readFile(file: 'steps.txt')
        println(data)
      }
    }
  }
