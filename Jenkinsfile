/* groovylint-disable CompileStatic, DuplicateStringLiteral */
pipeline {
    agent any
	environment
		dockerHome = tool 'mydocker'
		mavenHome = tool 'mymaven'
		PATH = "$dockerHome/bin:$mavenHome/bin/$PATH"
    stages {
        stage('Build') {
            steps {
                echo 'Build'
                // Run Maven version to check if Maven is working
				sh 'mvn --version'
				sh 'docker --version'
				echo "$env.BUILD_NUMBER"
				echo "$env.BUILD_id"
				echo "$env.JOB_NAME"
				echo "$env.BUILD_TAG"
				echo "$env.BUILD_URL"


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
            echo ' Devops Traing '
        }
        success {
            echo 'I Devops Traing 2'
        }
        failure {
            echo 'I am Not Devops'
        }
    }
}
