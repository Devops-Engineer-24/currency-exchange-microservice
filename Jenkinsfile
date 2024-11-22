pipeline {
    agent any

    environment {
        MAVEN_HOME = tool 'mymaven' // Maven tool name configured in Jenkins
        DOCKER_HOME = tool 'mydocker' // Docker tool name configured in Jenkins
        PATH = "${DOCKER_HOME}/bin:${MAVEN_HOME}/bin:${env.PATH}"
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

        stage('Compile') {
            steps {
                echo 'Compile Stage'
                sh 'mvn clean compile'
            }
        }

        stage('Integration Test') {
            steps {
                echo 'Integration Stage'
                // Handle potential failures for integration tests gracefully
                catchError(buildResult: 'UNSTABLE', stageResult: 'UNSTABLE') {
                    sh 'mvn failsafe:integration-test failsafe:verify'
                }
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
