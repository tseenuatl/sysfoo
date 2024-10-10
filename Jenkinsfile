pipeline {
	agent any

	triggers { pollSCM ('H/2 * * * *') }

	tools {
		maven 'Maven 3.6.1'
	}


	stages {
		stage( 'Build') {
			steps {
				echo 'Building..'
				sh 'mvn - worker/pom.xml compile'
		}
		}
		stage( 'Test') {
			steps {
				echo 'Testing..'
				sh 'mvn - worker/pom.xml test'
		}
		}
		stage( 'Package') {
			steps {
				echo 'Artifact creation..'
				sh 'mvn - worker/pom.xml package -DskipTests'
				archiveArtifacts artifacts: '**/target/*.jar, fingerprint:true
		}
		}
		Post {}
	}
}

