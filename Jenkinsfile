pipeline {
    agent any
tools {
        maven 'Maven5' // Match the name from Global Tool Configuration
    }
stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/RishiSathe/SpringBootAppCiCdDemo/tree/main', branch: 'main'
            }
        }
stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
    }
}
