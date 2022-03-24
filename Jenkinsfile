pipeline {
	agent any

	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'mymaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage('Build') {
			steps {
				sh 'mvn --version'
				sh 'docker version'
				echo "Building stage"
				echo "BRANCH_NAME - $env.BRANCH_NAME"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_URL - $env.BUILD_URL"
				
				
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
