pipeline {
    agent any

     environment {
        MAVEN_HOME = tool 'mymaven' // Use the name configured in Jenkins
        PATH = "${MAVEN_HOME}/bin:${env.PATH}"
		DOCKER_HOME = tool 'mydocker' // Use the name configured in Jenkins
        PATH = "${DOCKER_HOME}/bin:${env.PATH}"

    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Checkout Stage'
                sh 'mvn --version'
                sh 'docker --version'

                echo "Build Number: ${env.BUILD_NUMBER}"
                echo "Build ID: ${env.BUILD_ID}"
                echo "Job Name: ${env.JOB_NAME}"
                echo "Build Tag: ${env.BUILD_TAG}"
                echo "Build URL: ${env.BUILD_URL}"
            }
        }
        stage('Build') {
            steps {
                echo 'Build Stage'
                // Add your build commands here
            }
        }
        stage('Integration') {
            steps {
                echo 'Integration Stage'
                // Add your integration commands here
            }
        }
    }

    post {
        always {
            echo 'Post-build: Always runs'
        }
        success {
            echo 'Post-build: Build Successful'
        }
        failure {
            echo 'Post-build: Build Failed'
        }
    }
}