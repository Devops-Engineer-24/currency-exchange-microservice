pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo "Build"
            }
        }
        stage('Test') {
            steps {
                echo "Test"
            }
        }
        stage('Integration') {
            steps {
                echo "Integration"
            }
        }
    }

    post {
        always {
            echo "I am Devops"
        }
        success {
            echo "I Devops E2"
        }
        failure {
            echo "I am Not Devops"
        }
    }
}
