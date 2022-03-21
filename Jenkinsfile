pipeline {
	agent any
	stages {
		stage('Build') {
			steps {
				echo "Building stage"
			}
		}
		stage('Test') {
			steps {
				echo "Testing stage"
			}
		}
		stage('Integration Test') {
			steps {
				echo "Integration stage"
			}
		}
	}
	post{
		always {
			echo "Always Success"
		}
		success {
			echo "Success"
		}
		failure {
			echo "Failure"
		}
	}

}