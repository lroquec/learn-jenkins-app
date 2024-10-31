pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                }
            }
            steps {
                sh 'ls -la'
                sh 'npm --version'
                sh 'node --version'
                sh 'npm ci --verbose'
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