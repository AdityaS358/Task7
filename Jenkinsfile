pipeline {
    agent any
    stages {
	stage('Checkout'){
		steps{
			script{
				git branch: 'main', url: 'https://github.com/AdityaS358/Task7.git'
			}
		}
	}
        stage('Test') {
            steps {
                script {
                    // Checking Docker availability
                    bat 'docker info'
                }
            }
        }
        stage('Build') {
            steps {
                script {
                    // Building Docker image
                    bat 'docker build -t javaapp .'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    	// Run a container using the Docker image
                   	bat 'docker run -d --name javacontainer javaapp'
                    	// Fetch the Logs of the java File
			bat 'docker logs javacontainer'
                }
            }
        }
    }
}
