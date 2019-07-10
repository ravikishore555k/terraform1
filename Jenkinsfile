pipeline {
 agent any
 
String credentialsId = 'awsmysqldb'

try {
  stage('checkout') {
    node {
      cleanWs()
      checkout scm
    }
  }
}

 
 stage(‘Provision infrastructure’) {
 
 steps {
 dir(‘dev’)
 {
 sh ‘terraform init’
 sh ‘terraform plan -out=plan’
 // sh ‘terraform destroy -auto-approve’
 sh ‘terraform apply plan’
 }
 
 
 }
 }
 
 
 
 }
}
