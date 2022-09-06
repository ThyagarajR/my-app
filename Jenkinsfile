@Library("mylibs") _
pipeline {
    agent any
    tools {
        maven 'maven2'
    }
    stages{
        stage("maven Build"){
            steps{
                sh "mvn clean package"
            }
        }
        stage("Deploy To Dev"){
        steps{
            sshagent(['tomcat-dev']) {
               tomcatDeploy("tomcat-dev","ec2-user",["172.31.3.63"])
            }
        }
        }
    }
}
