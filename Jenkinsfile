pipeline {
    agent any

    stages {
        stage('cloning') {
            steps {
                  git branch: 'master', url: 'https://github.com/Joshtna/static-website-example.git'
            }
        }
      stage('deployment'){
          steps{
            //   sh 'aws s3 mb s3://demo2399'   
              sh 'aws s3 cp /var/lib/jenkins/workspace/s3-test s3://demo2399  --recursive' 
              sh 'aws s3 website s3://demo2399 --index-document index.html'
              sh 'aws s3api put-bucket-policy --bucket demo2399 --policy file://policy_s3.json'
          }
      } 
 
    }
}
