pipeline {
	agent any
        environment {
		PATH = "/opt/maven/bin:$PATH"
             }
	stages{
		stage('Buildingxx') {
			steps{
				sh '''
					echo "Build the war file"
					pwd
					mvn clean package
				   '''
			}
		}

		stage("Updateing Th tomcati") {
			steps{
				sh '''
					/opt/apache-tomcat-11.0.21/bin/shutdown.sh
					sleep 3

					sudo rm -rf /opt/apache-tomcat-11.0.21/webapps/irctc*

					sudo cp /home/ec2-user/ex-slave2/workspace/Pipeline-java-irctc2/target/irctc.war /opt/apache-tomcat-11.0.21/webapps/
					sudo /opt/apache-tomcat-11.0.21/bin/startup.sh
				  '''
			}
		}	
	}
}	
