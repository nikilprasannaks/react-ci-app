pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/your/repo.git' // update with your repo
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
      junit '**/test-results.xml' // optional if you configure Jest to output results
    }
  }
}
