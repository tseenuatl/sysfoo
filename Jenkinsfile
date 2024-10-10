pipeline {
	agent any

	triggers { pollSCM ('H/2 * * * *') }

	tools {
		maven 'Maven 3.9.6'
	}


	stages {
		stage( 'Build') {
			steps {
				echo 'Building..'
				sh 'mvn compile'
		}
		}
		stage( 'Test') {
			steps {
				echo 'Testing..'
				sh 'mvn test'
		}
		}
		stage( 'Package') {
			steps {
				echo 'Artifact creation..'
				sh 'mvn package -DskipTests'
				archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
		}
		}
	}
}

