pipeline {
	agent any
	stages {
		stage('Build') {
			steps {
			  echo "Build Phase"
			}
		}
		stage('Test') {
			steps {
			  echo "Test Phase"
			}
		}
		stage('Integration') {
			steps {
			  echo "Integration Phase"
			}
		}
	}

	post {
		always {
			echo "This will run for every run"
		}
		success {
			echo "You succeeded"
		}
		failure {
			echo "Please try again"
		}
	}
}