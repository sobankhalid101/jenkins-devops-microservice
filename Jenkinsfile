pipeline {
	agent any

	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'mymaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage('Checkout') {
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
		stage('Integration Test') {
			steps {
				sh "mvn failsafe:integration-test failsafe:verify"
			}
		}
		stage('Package') {
			steps {
				sh "mvn package -DskipTests"
			}
		}
		stage('Docker build') {
			steps {
				script {
					dockerImage = docker.build("sobankhalid101/currency-exchange-devops:${env.BUILD_TAG}")
				}
			}
		}
		stage('Docker push') {
			steps {
				script {
					docker.withRegistry('', 'dockerhub') {
						dockerImage.push();
						dockerImage.push('latest');
					}
				}
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
