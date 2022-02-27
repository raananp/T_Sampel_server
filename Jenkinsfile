pipeline {
    agent any
    tools {
        terraform 'terraform'
    }
    stages{
    stage('Git Pull') {
      steps {
          git branch: 'main', changelog: false, credentialsId: '0e94bf9e-995c-40ec-92c7-ce48c250d1fb', poll: false, url: 'https://github.com/raananp/raanancom'
      }
    }
    stage('Terraform INIT') {
      steps {
          sh 'terraform init'
      }
    }
    stage('Run Terraform') {
      steps {
          //sh label: '', script: 'terraform apply --auto-approve'
          sh label: '', script: 'terraform destroy --auto-approve'
      }
    }
  }
  
}
