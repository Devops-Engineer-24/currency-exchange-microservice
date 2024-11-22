pipeline {
    agent { docker { image 'maven:3.9.9-ibm-semeru-23-jammy' } }

    stages {
        stage('Build') {
            steps {
                echo "Build"
                // Run Maven version to check if Maven is working
                sh 'mvn --version'
            }
        }
        stage('Test') {
            steps {
                echo "Test"
                // Add your test logic here
            }
        }
        stage('Integration') {
            steps {
                echo "Integration"
                // Add your integration logic here
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
