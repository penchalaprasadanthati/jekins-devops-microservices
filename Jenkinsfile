pipeline {
	agent any
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}

	stages{
		stage('Checkout') {
			steps {
							
			}			
		}

		stage('Compile') {
			steps {				
				sh "mvn clean compile"							
			}			
		}

		stage('Test') {
			steps {
				sh "mvn Test"
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

		stage('Build Docker Image') {
			steps {
				
				script {
					dockerImage = docker.build("apprasadjava/currency-exchange:$env.BUILD_TAG");
				}
			}
		}

		stage('Push Docker Image') {
			steps {
				script {
					docker.withRegistry('','dockerhube');
					dockerImage.push();
					dockerImage.push('latest');
				}

			}
		}

	}
	
}
