pipeline {
    agent any

    environment {
        PATH = "/opt/homebrew/bin:/usr/local/bin:/usr/bin:/bin"
        JAVA_HOME = "/Library/Java/JavaVirtualMachines/jdk-21.jdk/Contents/Home"
    }

    stages {

        stage('Check Environment') {
            steps {
                sh 'java -version'
                sh 'mvn -version'
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
            echo 'Java project built successfully!'
        }

        failure {
            echo 'Build failed. Check the console output.'
        }
    }
}