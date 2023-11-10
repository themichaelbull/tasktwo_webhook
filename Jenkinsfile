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
            }
        }
        stage('Clone Repo'){
            steps {
                sh "git clone https://github.com/themichaelbull/tasktwo_webhook"
                sh "ls"
            }
        }
    }
}
