pipeline{
	agent any
	environment{
		DOCKER_CREDENTIALS("dockerHub")
		IMAGE_NAME="docker 1ms24mc102/react_app"
	}	
	stages{
		stage('Linking git repo){
			step{
				git url:https://github.com/1ms24mc102/repo ,branch:main
			}
		}
		stage('Building Docker Image'){
			step{
				script{
					dockerImage=docker.build("${IMAGE_NAME}:latest")
				}
			}
		}
		stage('Pushing image into dockerhub repo'){
			step{
				script{
					dockerImage=docker.push(${IMAGE_NAME}:latest")
				}
			}
		}
	}
}

#Design and implement a fully automated CI/CD pipeline for a React application using Git/GitHub, Jenkins and Docker. Deploy the containerized application on kubernetes
