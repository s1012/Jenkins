pipeline{
agent any
  stages{

      stage('terraform started') {
steps{

         sh 'echo "started.......... Webhook started....."'
}
}
  stage('git clone'){

     steps{
sh 'sudo rm -r *; sudo git clone https://github.com/s1012/Jenkins.git'
}
}
  stage('tfvars Create'){
        steps{
           sh 'sudo cp /root/main.tf  /var/lib/jenkins/workspace/s3/'
}
}  

   stage('terraform init'){
    steps{
       {
           sh 'terraform init'
           sh 'terraform plan -out=plan'
         // sh 'terraform apply plan'
         // sh 'terraform destroy -auto-approve' 
}
}
}  
stage('terraform plan'){
steps{

sh 'terraform plan -out=plan'
}
}
stage('terraform ended'){

 steps{
      sh ' echo "Ended....!!!"'
}
 }

}
}
