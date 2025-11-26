pipeline {
    agent any

    stages {
        stage('Pull Code') {
            steps {
                git branch: 'main',
                    url: 'your repo url'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t <yourwebname:1.0 or sometimg> .'
            }
        }

        stage('Stop Old Container') {
            steps {
                script {
                    sh 'docker rm -f <yourwebname> || true'
                }
            }
        }

        stage('Run New Container') {
            steps {
                sh 'docker run -d --name yourwebname(as you like) -p hostport:80 <yourwebname:1.0 or sometimg>'
            }
        }
    }
}

