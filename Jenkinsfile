pipeline {
  
  agent any  
  
  stages {
    stage('checkout') {
      steps {
        checkout scm
  	    }
    	}
    
    stage('Terraform initialize') {
      steps {
        sh 'terraform init'
      }
    }
    
    stage('Terraform plan') {
      steps {
        sh 'terraform plan -destroy tfplanout'
      }
    }
        
    stage('apply') {
      steps {
        sh 'terraform destroy -auto-approve'
        cleanWs()
      }
    }
  }
}
