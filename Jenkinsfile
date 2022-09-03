pipeline {
  agent any
  tools {
  maven 'maven2'
}
  stages{
  //  stage ("SCM Checkout") {
  //    steps{
  //      git credentialsId: '39dd5490-5b5e-4f5d-b678-32c4357b4f24', url: 'https://github.com/ThyagarajR/my-app/'
  //}
  //  }
    stage ("Maven Build") {
      steps {
        sh "mvn clean package"
  }
}
    stage ("Deploy to Dev"){
      steps{
        sshagent(['tomcat-dev']) {
          sh "mv target/*.war target/webapps.war"
          sh "scp -o StrictHostKeyChecking=no target/*.war ec2-user@172.31.3.63:/opt/tomcat9/webapps/"
          sh "ec2-user@172.31.3.63 /opt/tomcat9/bin/shutdown.sh"
          sh "ec2-user@172.31.3.63 /opt/tomcat9/bin/startup.sh"
       }
      }
    }
  }
}
