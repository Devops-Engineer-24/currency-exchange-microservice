/* groovylint-disable CompileStatic, DuplicateStringLiteral */
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build'
                // Run Maven version to check if Maven is working
				echo "Build"
				echo "BUILD.TAG_NUMBER - $env.BUILD_NUMBER"
				echo "$env.Build_id"
				echo "$env.JOB_NAME"
				echo "$env.BUILLD.TAG"


            }
        }
        stage('Test') {
            steps {
                echo 'Test'
            // Add your test logic here
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
            echo 'I am Devops'
        }
        success {
            echo 'I Devops E2'
        }
        failure {
            echo 'I am Not Devops'
        }
    }
}
