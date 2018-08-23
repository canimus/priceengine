pipeline {
  agent {
    docker {
      image 'python:3.6.5-slim'
    }

  }
  stages {
    stage('Build') {
      steps {
        echo 'Building..'
        sh 'pip install --upgrade pip'
      }
    }
    stage('Test') {
      steps {
        echo 'Testing..'
        sh 'python -V'
        sh 'pip list'
      }
    }
    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            echo 'Deploying....'
          }
        }
        stage('Destroy') {
          steps {
            mail(subject: 'BRO: Test', body: 'Email test', charset: 'UTF-8', from: 'herminio@iovio.com', to: 'bro@iovio.com')
          }
        }
      }
    }
  }
}