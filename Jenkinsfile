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
				sh 'mvn --version'
				echo "Build stage"
			}	
		}
		stage('Test') {
			steps {
				echo "Test stage"
			}
		}
		stage('Int Test') {
			steps {
				echo "Int Test stage"
			}	
		}
	}

}
