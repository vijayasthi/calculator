pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Running build automation'
		//bat 'py -m pip install flake8 pytest pytest-cov'
            }
		}
        stage('Test') {
            steps {
                echo 'Test build automation'
                bat 'pytest -v --cov'
			}
		}
	}
	    post {
        success {
            echo 'I succeeeded!'
	    echo "Succeeded Pipeline: ${currentBuild.fullDisplayName}"
            echo "${env.BUILD_URL}"
        }
        failure {
            echo 'I failed :('
	    echo "Failed Pipeline: ${currentBuild.fullDisplayName}"
            echo "${env.BUILD_URL}"
        }
    }
}
