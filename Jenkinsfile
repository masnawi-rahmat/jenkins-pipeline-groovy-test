#!groovy

def stage(String label, Closure cl) {
  println "The stage is ${label}"
  cl()
  println "Exit stage"
}

stage('Say Hello World') {
  println 'Hello World'
}

stage('Stage 2') {
  println "Hello Again"
}
