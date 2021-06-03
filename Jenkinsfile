pipeline{
	agent any
	stages{
		stage("Pull Latest Image"){
			steps{
				//sh 
				bat "docker pull vivek1334/selenium-docker"
			}
		}
		stage("Start Grid"){
			steps{
				//sh 
				bat "docker-compose up -d hub chrome firefox"
			}
		}
		stage("Run Test"){
			steps{
				//sh 
				bat "docker-compose up search-module book-flight-module"
			}
		}
	}
	post{
		always{
			archiveArtifacts artifacts: 'output/**'
			//sh 
			bat "docker-compose down"
			//sh 
			bat "sudo rm -rf output/"
		}
	}
}
