pipeline {
    agent {
        label 'ubuntu'
    }
    stages {
        stage('Cleanup Stage'){
            steps {
                sh "rm -rf *"
                sh "docker rm -f \$(docker ps -aq) || true"
                sh "docker rmi -f \$(docker images) || true"
                sh "docker rm -f \$(docker ps -aq) || true"
                sh "docker rmi -f \$(docker images) || true"
                sh "docker network delete new-network || true"
            }
        }
        stage('Clone Repo'){
            steps {
                sh "git clone https://github.com/themichaelbull/tasktwo_webhook"
                sh "cp -r tasktwo_webhook/* ./"
                sh "ls"
            }
        }
        stage('build'){
            steps {
                sh "docker network create -d bridge new-network
                sh "docker build -t nginxapp . -f nginx/Dockerfile --no-cache" 
            }
        }
    }
}
