pipeline {
	// agent any
	// agent { docker { image 'maven:sapmachine'} }
	agent { docker { image 'node:13.8'} }
	stages {
		stage('Build') {
			steps {
			  echo "Build Phase"
			  sh 'node --version'
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