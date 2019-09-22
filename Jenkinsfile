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
	}
}
