pipeline {
	// agent any
	agent { docker { image 'maven:3.6.3'} }
	stages {
		stage('Build') {
			steps {
			  echo "Build Phase"
			  sh 'mvn --version'
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