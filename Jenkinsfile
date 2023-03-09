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
          }
      } 
    }
}
