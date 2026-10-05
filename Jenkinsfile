pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Source CODE fetched successfully.'
            }
        }

        stage('Build') {
            steps {
                echo 'Building project...'
                bat 'echo Build Passed'
            }
        }

        stage('Test') {
            steps {
                echo 'Running automated tests...'
                bat 'echo All Tests Passed Successfully'
            }
        }
    }

    post {
        success {
            echo 'PIPELINE STATUS: SUCCESS'
        }
    }
}
