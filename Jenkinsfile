pipeline {
	agent any
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH ="$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage('Build'){
			steps{
				sh 'docker version'
				sh 'maven --version'
				echo "Build"
				echo "path - $PATH"
				echo "build number - $env.BUILD_NUMBER"
				echo "build id - $env.BUILD_ID"
				echo "job name - $env.JOB_NAME"
				echo "build url - $env.BUILD_URL"
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
