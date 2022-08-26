pipeline {
	agent any
	stages {

		stage('Build') {
			steps {
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
	} post {
		always {
			echo "I run always."
		}
	}


}
