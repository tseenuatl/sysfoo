pipeline {
	agent any

	stages {
		stage( 'one') {
			steps {
				echo 'one'
				sleep 5 
		}
		}
		stage( 'two') {
			steps {
				echo 'two'
				sleep 5
		}
		}
		stage( 'three') {
			steps {
				echo 'three'
				sleep 5
		}
		}
	}

post {
	always {
		echo 'four post'
     }
   }

}

