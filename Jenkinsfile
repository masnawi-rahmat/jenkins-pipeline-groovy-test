/*node {
  stage('Say Hello') {
    echo 'Hello World'
  }
} */

def stage(String label, Closure cl) {
  println "The stage is ${label}"
  cl()
  println "Exiting the stage"
}

stage('Say Hello World') {
  println 'Hello World'
}

stage('Stage 2') {
  println "Hello Again"
}

stage('Read Steps File') {
  readstepfile = readFile('steps.txt')
  println readstepfile
}
