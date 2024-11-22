pipeline {
    agent { docker {image 'maven:3.9.9-ibm-semeru-23-jammy'}}
    
    stages {
        stage('Build') {
            steps {
                echo "Build"
				sh 'mvn --version'
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
