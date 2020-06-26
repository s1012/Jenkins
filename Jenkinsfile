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
           sh 'sudo cp /root/vars.tf  ./s3/'
}
}  

   stage('terraform init'){
    steps{
    sh 'sudo /root/terraform init ./s3'
}
}
  
stage('terraform plan'){
steps{

 sh 'ls ./jenkins; sudo /root/git/testing/Jenkins/terraform plan ./s3'
}
}

stage('terraform ended'){

 steps{
      sh ' echo "Ended....!!!"'
}
 }

}
}
