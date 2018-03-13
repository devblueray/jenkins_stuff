pipeline {
    agent { docker { image 'gradle:alpine' } }
    
    environment {
	TEST=1
	ENGINE='sql'
       }

    stages {
        stage('build') {
            steps {
		echo "${WORKSPACE}"
		sh './gradlew build'
           	 }
        }
	
	stage('Test') {
	   steps {
		sh './gradlew check'
	   }
	}
    }
}

   post {
   	always {
		archiveArtifacts artifacts: 'build/libs/**/*.jar', fingerprint: true
		junit 'build/reports/**/*.xml'
	}
        
	success {
		echo 'This runs on success'
	}
	
	failure {
		echo 'This runs on failure'
	}
	
	changed {
		echo 'This runs if the state of the pipeline changes, ex: Failure to Success'
	}
  }


