pipeline {
    agent any
    stages {
        stage('Cleanup Stage'){
            steps {
                sh "rm -rf *"
                sh "docker rm -f \$(docker ps -aq) || true"
                sh "docker rmi -f \$(docker images) || true"
                sh "docker rm -f \$(docker ps -aq) || true"
                sh "docker rmi -f \$(docker images) || true"
                sh "docker network rm new-network || true"
            }
        }
        stage('build'){
            steps {
                sh "docker network create -d bridge new-network"
                sh "pwd"
                sh "ls"
                sh "docker build -t nginxapp . -f nginx/Dockerfile --no-cache" 
            }
        }
    }
}
