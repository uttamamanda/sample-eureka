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
				sh "mvn deploy"
			}
		}
		
		/*stage('Docker Push'){
		steps{
		sh "docker tag eurekaserver:latest 130.211.215.96:8081/repository/eurekaserver"
		sh "docker push 130.211.215.96:8081/repository/eurekaserver"
		}
		} */  
	}
}
