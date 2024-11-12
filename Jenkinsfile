pipeline { 
	agent any
	stages {
		stage('Git-Checkout') {
			steps {
					echo "Checking out from GIT Repo";
		}
	}
		
		stage('Build')	{
			steps {
					echo "Building the checked-out project!";
					bat 'Build.bat'
		}
	}

		stage('Unit-Test') {
			steps {
					echo "Running JUnit Tests";
					bat 'Unit.bat'
		}
	}		
	
		stage('Quality-Gate') {
			steps {
					echo "Verifying Quality Gate";
					bat 'Quality.bat'
		}
	}		
		stage('Deploy') {
			steps {
					echo "Deploying to Stage evvironment for more tests";
					bat 'Deploy.bat'
		}
	}	
}

	post {
		always {
			echo 'This will always run'
		}
		success {
			echo 'This will run only if successful'
		}
		failure	{
			echo 'This will run only if failed'
		}
		unstable {
			echo 'This will run only if the run was marked as unstable'			
		}
		changed {
			echo 'This will run only if the state of the Pipeline has changed'				
			echo 'For example, If the Pipeline was previously failing but is now successful'							
		}
	}
}
