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
                sh "git clone https://github.com/themichaelbull/tasktwo_webhook"
                sh "ls"
                sh "cd tasktwo_webhook/nginx && docker build -t nginxapp . -f Dockerfile --no-cache "
                sh "cd tasktwo_webhook/flask-app && docker build -t myapp . --no-cache"
                sh "cd tasktwo_webhook/db && docker build -t mysqldatabase . --no-cache"
            }
        }
    }
}
