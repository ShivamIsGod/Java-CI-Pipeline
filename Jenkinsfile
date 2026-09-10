pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/ShivamIsGod/Java-CI-Pipeline.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean compile'
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

    post {
        success {
            echo '🎉 Java project built successfully!'
        }

        failure {
            echo '❌ Build failed. Check the console output.'
        }
    }
}
