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
    sh'ls /var/lib/jenkins/workspace/s3; sudo /root/terraform init /var/lib/jenkins/workspace/s3'
}
}
  
stage('terraform plan'){
steps{

 sh 'ls /var/lib/jenkins/workspace/s3; sudo /root/terraform plan /var/lib/jenkins/workspace/s3'
}
}

stage('terraform ended'){

 steps{
      sh ' echo "Ended....!!!"'
}
 }

}
}
