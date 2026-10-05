pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Source code fetched from GitHub...'
            }
        }

        stage('Compile') {
            steps {
                echo 'Compiling Java sources...'
                bat 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                echo 'Running unit tests...'
                bat 'mvn test'
            }
        }

        stage('Package') {
            steps {
                echo 'Packaging application...'
                bat 'mvn package -DskipTests'
            }
        }
    }

    post {
        always {
            junit allowEmptyResults: true, testResults: '**/target/surefire-reports/*.xml'
        }
        success {
            echo '====================================='
            echo 'STATUS: SUCCESS (MAVEN BUILD PASSED)'
            echo '====================================='
        }
        failure {
            echo 'STATUS: FAILED'
        }
    }
}
