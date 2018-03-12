pipeline {
    agent { docker { image 'maven:3.3.3' } }
    
    environment {
	TEST=1
	ENGINE='sql'
       }

    stages {
        stage('build') {
            steps {
                sh 'mvn --version' 
		sh 'echo "Hello World"'
 		sh 'printenv'
            }
        }
    }
   post {
   	always {
		echo 'This always runs'
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
}

