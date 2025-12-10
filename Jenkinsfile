pipeline {
	agent any
	environment {
		dockerHome = tool 'mydocker'
		mavenHome = tool 'mymaven'
		PATH ="$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage('Build'){
			steps{
				sh 'docker version'
				sh 'maven --version'
				echo "Build"
			}			
		}
		stage('Test'){
			steps{
				echo "Test"
			}			
		}
		stage('Integration Test'){
			steps{
				echo "Integration Test"
			}
		}
	}
	
}
