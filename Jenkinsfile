pipeline {
  agent any
  tools {
  maven 'maven2'
}
  stages{
    stage ("SCM Checkout") {
      steps{
        git credentialsId: '39dd5490-5b5e-4f5d-b678-32c4357b4f24', url: 'https://github.com/ThyagarajR/my-app/'
}
    }
    stage ("Maven Build") {
      steps {
        sh "mvn clean package"
  }
}
  }
}
