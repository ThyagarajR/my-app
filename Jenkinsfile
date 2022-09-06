pipeline{
    
    agent {
        label "linux"
    }
    
    stages{
        stage("Stage A"){
            steps{
                echo "Post build demo"
            }
        }
        stage("Stage B"){
            steps{
                sh "xxxxxx"
            }
        }
    }
   post {
      success {
        echo "Send success email"
      }
      failure {
        echo "Send failure email"
      }
    }
}
