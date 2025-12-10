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
				echo "path - $PATH"
				echo "build tag - $env.BUILD_TAG"
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
