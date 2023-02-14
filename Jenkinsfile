pipeline{
  agent{
    docker{
      image 'node:14'
    }
  }
  stages {
    stge('Clone Repository') {
      steps {
        git branch: 'main',
          url : 'https://github.com/azfar-rayan/PES1UG20CS453_Jenkins.git'
      }
    }
    stage('Install Dependencies') {
      steps {
        sh 'npm install'
      }
    }
    stage('Build Application') {
      steps {
        sh 'npm test'
      }
    }
    stage('Push Docker Image') {
      steps {
        sh 'docker build -t azfarrayan/jenkins:PES1UG20CS453 .'
        sh 'docker push azfarrayan/jenkins:PES1UG20CS453'
      }
    }
  }
}
