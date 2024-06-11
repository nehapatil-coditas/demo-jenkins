pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        bat(script: 'echo "helloooo..."', returnStatus: true)
        echo '"Test Stage"'
      }
    }

    stage('Build') {
      steps {
        echo 'Build Stage'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deployed on Production...'
      }
    }

  }
}