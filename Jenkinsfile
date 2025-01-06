pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        echo 'Checkout the GitHub repository'
        git(url: 'https://github.com/uncle-bob-24/cicd-pipeline.git', branch: 'main')
      }
    }

    stage('Build') {
      steps {
        echo 'Build the application'
        sh 'scripts/build.sh'
      }
    }

    stage('Test') {
      steps {
        echo 'Run tests'
        sh 'scripts/test.sh'
      }
    }

    stage('Build Docker Image') {
      steps {
        script {
          echo "Build the Docker image"
          docker.build('myapp256')
        }

      }
    }

    stage('Push Docker Image') {
      steps {
        script {
          withDockerRegistry([credentialsId: 'dockerhub-credentials', url: 'https://index.docker.io/v1/']) {
            // Push the Docker image to the Docker registry
            docker.image('myapp256').push('latest')
          }
        }

      }
    }

  }
}