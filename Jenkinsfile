/* groovylint-disable CompileStatic, DuplicateStringLiteral */
pipeline {
    agent any

    environment {
        DOCKER_HOME = tool 'mydocker'
        MAVEN_HOME = tool 'mymaven'
        PATH = "${DOCKER_HOME}/bin:${MAVEN_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Checkout'
                // Run Maven and Docker version to verify tools
                sh 'mvn --version'
                sh 'docker --version'
                
                // Print environment variables
                echo "Build Number: ${env.BUILD_NUMBER}"
                echo "Build ID: ${env.BUILD_ID}"
                echo "Job Name: ${env.JOB_NAME}"
                echo "Build Tag: ${env.BUILD_TAG}"
                echo "Build URL: ${env.BUILD_URL}"
            }
        }
        stage('Build') {
            steps {
                echo 'Build'
                // Add your build logic here
            }
        }
        stage('Integration') {
            steps {
                echo 'Integration'
                // Add your integration logic here
            }
        }
    }

    post {
        always {
            echo 'DevOps Training Completed'
        }
        success {
            echo 'Build failed "Success!"'
        }
        failure {
            echo 'Build failed. Debug and try again.'
        }
    }
}
