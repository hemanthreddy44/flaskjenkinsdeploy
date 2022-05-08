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
                  sh "aws ecs update-service --cluster abhi --service reddd --task-definition maddy:8 --force-new-deployment"
              }
         }
             }
        }
