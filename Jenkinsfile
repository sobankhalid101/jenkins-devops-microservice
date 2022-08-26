pipeline {
	agent any

	stages{
		stage('Build') {
			echo "Build stage"
		}
		stage('Test') {
			echo "Test stage"
		}
		stage('Int Test') {
			echo "Int Test stage"
		}
	} post {
		always {
			echo "I run always."
		}
	}


}
