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
          docker.build('react-test-app')
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
