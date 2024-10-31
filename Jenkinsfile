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
                sh 'ls -la'
                sh 'npm --version'
                sh 'node --version'
                sh 'rm -rf node_modules'
                sh 'npm cache clean --force'
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