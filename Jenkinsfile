pipeline {
     agent any
environment {
    IMAGE_REPO = "hemanthhr/flaskhello"
    // Instead of hemanthhr, use your git username
}     
     stages {
         stage('Build Docker Image') {
              steps {
                  sh "ls"
                  sh " docker image build -t  ${env.IMAGE_REPO}:${env.GIT_COMMIT} ."
              }
         }
         stage('deploy latesh image') {
              steps {
                  sh "docker stop demo"
                  sh "docker rm demo "
                  sh "docker run --restart always --name demo -p 5000:5000 -d ${env.IMAGE_REPO}:${env.GIT_COMMIT}"
              }
         }
             }
        }
