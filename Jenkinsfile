pipeline {
	agent any
	stages {
		stage('Get Checkout') {
			steps {
					echo "Checking out from Git Repo";
					git branch: 'main', url: 'https://github.com/sidj5/jenkins_pipeline.git'
			}
        }
		
		stage('Build') {
			steps {
					echo "Building the checked out project";
			}
        }

		stage('Unit-Test') {
			steps {
					echo "Performing JUnit tests";
			}
		}
			
		stage('Quality Gate') {
			steps {
					echo "Verifying quality gates";
			}
		}

		stage('Deploy') {
			steps {
					echo "Deploying the project to the staging environment";
			}
		}
	}
}
