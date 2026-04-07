pipeline {
	agent any
        environment {
		PATH = "/opt/maven/bin:$PATH"
	stages{
		stage('Building') {
			steps{
				sh '''
					echo "Build the war file"
					pwd
					mvn clean package
				   '''
			}
		}
	}
}	
