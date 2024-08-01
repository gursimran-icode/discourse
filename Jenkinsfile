pipeline {
  agent any
  stages {
    stage("verify tooling") {
      steps {
        sh '''
          docker version
          docker info
          docker compose version
          curl --version
        '''
      }
    }
    stage('Prune Docker data') {
      steps {
      sh '''
          docker version
          docker info
          docker compose version
          curl --version
        '''
      }
    }
    stage('Start container') {
      steps {
        sh './launcher rebuild app'
      }
    }
    stage('Run tests against the container') {
      steps {
        sh 'curl http://forumstaging.icodestaging.in'
      }
    }
  }
  post {
    failure {
   sh '''
          docker version
          docker info
          docker compose version
          curl --version
        '''
    }
  }
}
