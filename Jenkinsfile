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
                sh 'npm ci --cache .npm'
                sh 'npm run build'
            }
        }
        stage('test') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }          
            steps {
                 sh '''
                    test -f build/index.html
                    npm test
                 '''
            }
        }
    }
    post {
      always {
        junit 'test-results/junit.xml'
      }
    }
}