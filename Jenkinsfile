pipeline {
    agent { docker { image 'maven:3.3.3' } }
    stages {
        stage('build') {
            steps {
                sh 'mvn --version' 
		sh 'echo "Hello World"'
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
	chanced {
		echo 'This runs if the state of the pipeline changes, ex: Failure to Success'
	}
	}
}

