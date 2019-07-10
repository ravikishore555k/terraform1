pipeline {
 agent any
  
 stages {
 stage('checkout') {
 steps {
 git branch: 'terraform1'. url:'https://github.com/ravikishore555k/terraform1.git'
 }
 }
 stage('Set Terraform path') {
 steps {
 script {
 def tfHome = tool name:'Terraform'
 env.PATH = "${tfHOME}:${env.PATH}"
 }
 sh 'terraform --version'
 }
 }
 stage('Provision infrastructure')
 {
 
 steps {
 dir('dev')
 {
 sh 'terraform init'
 sh 'terraform plan -out=plan'
 //sh 'terraform destroy -auto-approve'
 sh 'terrraform apply plan'
  }
  }
  }
  }
 }
 
 
