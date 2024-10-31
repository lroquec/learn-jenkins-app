pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh 'echo "Hello World"'
                sh 'npm --version'
                sh 'node --version'
                sh 'npm ci'
                sh 'npm run build'
            }
        }
        stage('test') {
          steps {
            echo 'test stage'
          }
        }
    }
}