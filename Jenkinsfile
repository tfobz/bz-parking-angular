pipeline {
  agent any
  stages {
    stage('upload') {
      steps {
	sh 'test -f public/index.html'
        s3Upload(bucket: 'it.bz.parking', acl: 'PublicRead', file: './public')
      }
    }
  }
   environment {
     AWS_ACCESS_KEY_ID = credentials('AWS_ACCESS_KEY_ID')
     AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
   }
}