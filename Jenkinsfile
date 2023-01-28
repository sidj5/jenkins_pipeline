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
					bat 'Build.bat'
			}
        }

		stage('Unit-Test') {
			steps {
					echo "Performing JUnit tests";
					bat 'Unit.bat'
			}
		}
			
		stage('Quality Gate') {
			steps {
					echo "Verifying quality gates";
					bat 'Quality.bat'
			}
		}

		stage('Deploy') {
			steps {
					echo "Deploying the project to the staging environment";
					bat 'Deploy.bat'
			}
		}
	}
}
