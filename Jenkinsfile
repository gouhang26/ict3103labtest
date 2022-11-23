pipeline {
	agent any
	stages {
		stage('OWASP DependencyCheck') {
 			steps {
 		 		dependencyCheck additionalArguments: '--format HTML --format XML --disableYarnAudit --enableExperimental', odcInstallation: 'Default'
 		  	}
 		 }
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}