pipeline {
  agent {
    docker {
      image 'node:1a’
    }
  }
  stages {
    stage('Clone repository’) {
      steps {
          git branch: ‘main’,
          url: "https://github.com/<user>/<repo>.git’
      }
   }
   stage('Install dependencies’) {
    steps {
      sh 'npm install'
      }
  }
    stage('Build application’) {
    steps {
      sh "npm run build’
  }
}
  stage('Test application’) {
    steps {
      sh "npm test’
    }
  }
   stage('Push Docker image") {
    steps {
        sh 'docker build -t azfarrayan/jenkins:PES1UG20CS453 .' 
        sh 'docker push azfarrayan/jenkins:PES1UG20CS453'
      }
    }
  }
}
