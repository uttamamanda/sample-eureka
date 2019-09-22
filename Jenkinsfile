pipeline{
 agent any //jdk8
 stages	{
		stage('Build'){
			steps {
				sh "mvn clean install"
			}
		}
		stage('Sonar'){
			steps {
				sh "mvn sonar:sonar"
			}
		}
		stage('Docker Build'){
			steps {
				sh "docker build -t eurekaserver:latest ."
				}
		}
		stage('Nexus Upload'){
			steps{
			sh "curl -v -u admin:admin --upload-file eureka-server/target/eureka-server-0.0.1-SNAPSHOT.jar http://130.211.215.96:8081/repository/maven-releases/org/exampledriven/1.0/eureka-server.jar"
			}
		}   
	}
}
