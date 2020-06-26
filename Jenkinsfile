pipeline {
 agent any
 
 stages {
 stage(‘checkout’) {
 steps {
 sh 'sudo git clone https://github.com/s1012/Jenkins.git’
 }
 }
 stage(‘Set Terraform path’) {
 steps {
 script {
 def tfHome = tool name: ‘Terraform’
 env.PATH = “${tfHome}:${env.PATH}”
 }
 sh ‘terraform — version’
 
 }
 }
 
 stage(‘Provision infrastructure’) {
 
 steps {
 dir(‘Jenkins’)
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
