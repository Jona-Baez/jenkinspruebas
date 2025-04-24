pipeline {
  agent any

  environment {
    AWS_ACCESS_KEY_ID     = credentials('aws-access-key-id')       // ID de la clave configurada en Jenkins
    AWS_SECRET_ACCESS_KEY = credentials('aws-secret-access-key')   // Secret configurado en Jenkins
    AWS_REGION            = 'us-east-1'
    TF_IN_AUTOMATION      = 'true'
  }

  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/Jona-Baez/jenkinspruebas'
      }
    }

    stage('Terraform Init') {
      steps {
        sh 'terraform init'
      }
    }

    stage('Terraform Plan') {
      steps {
        sh 'terraform plan'
      }
    }

    stage('Terraform Apply') {
      steps {
        sh 'terraform apply -auto-approve'
      }
    }
  }
}
