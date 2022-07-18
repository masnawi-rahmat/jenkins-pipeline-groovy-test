def code

node('java-agent') {
  stage('Checkout') {
    checkout scm
  }

  stage('Load') {
    code = load 'example.groovy'
  }

  stage('Execute') {
    code.example1()
  }
}

code.example2()

/* 
node {
    stage('test') {
        echo 'hello'
    }
} 
*/
