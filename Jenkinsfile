pipeline {
	agent any

	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'mymaven'
		PATH = "$PATH:$dockerHome/bin:$mavenHome/bin"
	}

	stages {
		stage('Build') {
			steps {
				sh 'mvn --version'
				sh 'docker version'
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
