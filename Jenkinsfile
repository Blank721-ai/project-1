pipeline {
    agent any

    stages {
        stage('Pull Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Blank721-ai/project-1.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t akm_web:1.0 .'
            }
        }

        stage('Stop Old Container') {
            steps {
                script {
                    sh 'docker rm -f akm_web || true'
                }
            }
        }

        stage('Run New Container') {
            steps {
                sh 'docker run -d --name akm_web -p 8086:80 akm_web:1.0'
            }
        }
    }
}
