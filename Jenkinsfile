pipeline {
    agent any
    stages {
      stage('AWS Credentials') {
        steps {
          withCredentials(
            [[
              $class: 'AmazonWebServicesCredentialsBinding', 
              accessKeyVariable: 'AWS_ACCESS_KEY_ID', 
              credentialsId: 'aws-ansible', 
              secretKeyVariable: 'AWS_SECRET_ACCESS_KEY'
              ]]) {
                sh 'packer build -var aws_access_key=${AWS_ACCESS_KEY_ID} -var aws_secret_key=${AWS_SECRET_ACCESS_KEY} example4.json'
              }
      }
    }
  }
}