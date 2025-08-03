pipeline {
    agent any

    tools {
        maven 'Maven5' // Make sure this matches the name under Global Tool Configuration
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/RishiSathe/SpringBootAppCiCdDemo.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean'
            }
        }

        stage('Compile') {
            steps {
                sh 'mvn compile'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test -DskipTests=true'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
    }

    post {
        always {
            echo "########  Printing Always from Post ########"
        }
        success {
            echo "########  Printing Success from Post ########"
        }
        failure {
            echo "########  Printing Failure from Post ########"
        }
    }
}
