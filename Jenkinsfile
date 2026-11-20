
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
                echo 'Compiling Java Application'
                bat 'javac Test.java'
            }
        }

        stage('Test') {
            steps {
                echo 'Executing Java Application Test'
                bat 'java Test'
            }
        }

        stage('Run Application') {
            steps {
                echo 'Running Java Application'
                bat 'java Test'
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
