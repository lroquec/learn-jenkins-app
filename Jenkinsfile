pipeline {
    agent any

    stages {
        stage('Hello') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh ' echo "Hello World"'
                sh 'npm --version'
            }
        }
    }
}