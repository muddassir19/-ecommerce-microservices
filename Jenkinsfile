pipeline{
    agent any

    stages {
        stage('checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github', url: 'https://github.com/muddassir19/-ecommerce-microservices.git']])
            }
        }

        stage('Build user-service Microservice') {
            steps {
                dir('user-service'){
                    sh './mvnw clean package'
                }
            }
        }
    }
}