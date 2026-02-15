pipeline {
    agent {
        docker {
            image 'node:18'
        }
    }

    stages {

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t jenkins-node-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 3001:3000 jenkins-node-app'
            }
        }
    }
}
