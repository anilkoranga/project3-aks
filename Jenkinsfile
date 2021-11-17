pipeline{
	agent any
	environment {
		DOCKERHUB_CREDENTIALS=credentials('dockerhub-creds')
	}
	stages {
       
		stage('Build') {

			steps {
				sh 'docker build -t anilkoranga/task2:latest .'
			}
		}
		stage('Login') {

			steps {
				sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			}
		}
		stage('Push') {

			steps {
				sh 'docker push anilkoranga/task2:latest '
			}
		}
	}

}
