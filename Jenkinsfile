def pipeline

node {
  stage('Checkout') {
    checkout scm
  }

  stage('Load') {
    pipeline = load 'example.groovy'
    pipeline.example1()
  }
  pipeline.example2()
