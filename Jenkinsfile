pipeline {
  agent any
  stages {
    stage('checkout') {
      parallel {
        stage('checkout') {
          steps {
            sh 'echo "checkout"'
            sleep 1
            sh 'echo "build"'
          }
        }
        stage('build') {
          steps {
            sh 'echo "build"'
          }
        }
        stage('staticcheck') {
          steps {
            sh 'echo "static code check "'
          }
        }
      }
    }
    stage('docker build') {
      steps {
        sh 'echo "docker build "'
      }
    }
    stage('docker push') {
      steps {
        sh 'echo "docker push"'
      }
    }
    stage('docker deploy') {
      steps {
        sh 'echo "docker deploy"'
      }
    }
    stage('health check') {
      steps {
        sh 'echo "health check"'
      }
    }
    stage('switch loadbalancer') {
      steps {
        sh 'echo "update upstream in nginx"'
      }
    }
    stage('done') {
      steps {
        sh 'echo "done"'
      }
    }
  }
  environment {
    fore = 'true'
  }
}