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
   stage('terraform init'){
    steps{
    sh 'sudo /root/git/testing/terraform init ./s3'
}
}
}
}
