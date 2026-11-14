pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building Java application'
                bat 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing Java application'
                bat 'mvn test'
            }
        }

        stage('Run Application') {
            steps {
                bat 'mvn exec:java'
            }
        }
    }

    post {
        success {
            echo 'CI pipeline completed successfully'
        }

        failure {
            echo 'CI pipeline failed'
        }
    }
}
