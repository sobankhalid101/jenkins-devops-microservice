pipeline {
	//agent any
	agent {
		docker {
			image 'maven:3.6.3'
		}
	}
	stages {
		stage('Build') {
			steps {
				sh 'maven --version'
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