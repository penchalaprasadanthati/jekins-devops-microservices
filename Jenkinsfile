pipeline {
	agent any
	enviroment{
		dockerHome = tool 'mydocker'
		mavenHome = tool 'myMaven'
		PATH ="$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage('Build'){
			steps{
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
