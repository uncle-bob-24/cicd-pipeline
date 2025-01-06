pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Checkout'
      }
    }

    stage('Test') {
      steps {
        echo 'Build'
        sh '''
                cd scripts
                ./build.sh
                '''
      }
    }

    stage('Deliver') {
      steps {
        echo 'Test'
        sh '''
                cd scripts
                ./test.sh
               '''
      }
    }

  }
}