/* groovylint-disable CompileStatic, DuplicateStringLiteral */
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build'
                // Run Maven version to check if Maven is working
                sh 'mvn --version'
				echo "Builld"
				echo "Build_Number - $env.Build_Number"
				echo "$env.Build_id"

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
