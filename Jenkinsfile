pipeline {
  agent any
  stages {
    stage('Preparation') {
      steps {
        script {
          sh '''
          docker stop samplerunning || true
          docker rm samplerunning || true
          '''
        }
      }
    }
    stage('Build') {
      steps {
        build job: 'BuildSampleApp'
      }
    }
    stage('Results') {
      steps {
        build job: 'TestSampleApp'
      }
    }
  }
}
