pipeline{
agent { label 'slave1' }
stages{
    stage('Checkout'){
        steps{
            git branch: 'main', url : "https://github.com/maorHaim/jenkins_terraform.git"
        }
    }
    stage('Terraform init'){
        steps{
            sh 'terraform init'
        }
    }
    stage('Terraform apply'){
        steps{
              sh 'sudo terraform apply --auto-approve'
        }
    }
}
 post {
        always {
            deleteDir()
        }
    }
    
}