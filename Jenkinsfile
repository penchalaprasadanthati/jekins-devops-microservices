pipeline {
	agent {
		docker {
            image 'maven:3.9.6-eclipse-temurin-17'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
	}
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH ="$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage('Checkout'){
			steps{
				sh 'maven --version'				
			}			
		}

		stage('Compile'){
			steps{				
				sh "mvn clean install"							
			}			
		}
		stage('Test'){
			steps{
				sh "mvn Test"
			}			
		}
		stage('Integration Test'){
			steps{
				sh "mvn failsafe:integration-test failsafe:verify"
			}
		}
	}
	
}
