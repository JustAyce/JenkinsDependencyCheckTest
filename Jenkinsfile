pipeline {
	agent any
	stages {
		stage('Checkout SCM') {
			steps {
				// git '/home/JenkinsDependencyCheckTest'
				git 'https://github.com/JustAyce/JenkinsDependencyCheckTest.git'
			}
		}

		stage('OWASP DependencyCheck') {
			steps {
				dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: 'Default'
			}
		}
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}