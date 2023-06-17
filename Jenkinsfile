pipeline {
  agent any
  stages {
    stage ('Publish to ECR') {
      steps {
          sh 'docker login -u AWS -p $(aws ecr-public get-login-password - -region us-east-1) public.ecr.aws/e8g7n1t6'
          sh 'docker build -t ecr-demoimg .'
          sh 'docker tag ecr-demoimg:latest public.ecr.aws/e8g7n1t6/ecr-demoimg:""$BUILD_ID""'
          sh 'docker push public.ecr.aws/e8g7n1t6/ecr-demoimg:""$BUILD""'
       }
    }
  }
}
