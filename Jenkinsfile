pipeline {
	agent any 
	stages {
		stage ('Version Maven') {
			steps {
				sh 'MAVEN_HOME="/opt/apache-maven-3.8.6/bin"'
				sh '$MAVEN_HOME/mvn --version'
			}		
		}
		stage ('Creation de fichier exemple') {
			steps {
				sh 'touch exemple.txt'
				sh 'echo "Exemple d'un pipeline" >> exemple.txt'
			}
		}	
	}
}
