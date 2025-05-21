pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/nikilprasannaks/react-ci-app'
      }
    }

    stage('Build Docker Image') {
      steps {
        script {
          docker.build('react-test-app')
        }
      }
    }

    stage('Run Tests in Docker') {
      steps {
        script {
          docker.image('react-test-app').inside {
            sh 'npm test'
          }
        }
      }
    }
  }

  post {
    always {
      echo 'Build finished'
    }
  }
}
