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
        stage('Docker Run'){
            steps {
                sh 'ls'
            }
        }
    }
}
