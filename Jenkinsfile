pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Build"
                sh '''
                cd scripts
                ./build.sh
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Test"
                sh '''
                cd scripts
                ./test.sh
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver'
                sh '''
                docker build -t build1  
                '''
            }
        }
    }
}
