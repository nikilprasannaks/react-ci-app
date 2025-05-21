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

    stage('Run Tests') {
      steps {
        script {
          docker.image('react-test-app').inside {
            sh 'npm install'       // <-- Ensure this is run
            sh 'npm test'          // <-- Now this will find react-scripts
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
