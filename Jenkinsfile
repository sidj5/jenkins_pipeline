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
					sh 'Build.sh'
			}
        }

		stage('Unit-Test') {
			steps {
					echo "Performing JUnit tests";
					sh 'Unit.sh'
			}
		}
			
		stage('Quality Gate') {
			steps {
					echo "Verifying quality gates";
					sh 'Quality.sh'
			}
		}

		stage('Deploy') {
			steps {
					echo "Deploying the project to the staging environment";
					sh 'Deploy.sh'
			}
		}
	}
}
