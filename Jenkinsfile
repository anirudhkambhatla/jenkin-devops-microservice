pipeline {
	agent any
	// agent { docker { image 'maven:3.9.6'} }
	// agent { docker { image 'node:13.8'} }
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage('Checkout') {
			steps {
			  echo "Build Phase"
			  sh 'mvn --version'
			  sh 'docker version'
			  echo "Build"
			  echo "PATH - $PATH"
			  echo "BUILD_NUMBER - $env.BUILD_NUMBER"
			  echo "BUILD_ID -- $env.BUILD_ID"
			  echo "JOB_NAME --$JOB_NAME"
			  echo "BUILD_TAG --$env.BUILD_TAG"
			  echo "BUILD_URL --$env.BUILD_URL"
			}
		}
		stage('Compile') {
			steps {
			  sh "mvn clean compile"
			}
		}
		stage('Test') {
			steps {
			  sh "mvn test"
			}
		}

		stage('Integration') {
			steps {
			  sh "mvn test"
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