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
                    ls -lah
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    ls -lah
                '''
            }
        }
        stage('Test') {
            steps {
                echo 'Test stage'
            }
        }

    }
}
