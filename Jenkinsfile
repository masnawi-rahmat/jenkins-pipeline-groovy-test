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
  def readstepfile = readFile(file: 'steps.txt')
  println(readstepfile)
}


/*stage('read') {
           steps {
               script {
                   //def data = readFile(file: 'zorg.txt')
                   def data = readFile(file: 'sometext.txt')
                   //data.split('\n') 
                   println(data)
                   //println(line)
               }
           }
       }*/
