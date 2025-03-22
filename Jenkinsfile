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
                sh '''
                    ls -latrh
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    ls -latrh
                '''
            }
        }
        stage('Test') {
            steps {
                sh 'echo "This is the test stage..."'
            }
        }
    }
}
