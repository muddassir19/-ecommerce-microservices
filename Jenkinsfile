pipeline{
    agent any
    environment {
        JAVA_HOME = '/usr/lib/jvm/java-21-amazon-corretto.x86_64'
        PATH = "${env.JAVA_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github', url: 'https://github.com/muddassir19/-ecommerce-microservices.git']])
            }
        }

        stage('Build user-service Microservice') {
            steps {
                dir('user-service'){
                    sh 'chmod +x mvnw'
                    sh 'java -version'
                    sh './mvnw clean package'
                }
            }
        }
    }
}