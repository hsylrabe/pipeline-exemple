pipeline {
	agent any
	parameters {
		string(name: 'BRANCH', defaultValue: 'master', description: 'Name of the branche to use.')
	}
	stages {
		stage ('Version Maven') {
			steps {
				script {
					sh 'echo ${params.BRANCH}"'
					if (params.BRANCH == 'develop') {
						sh '''
						export MAVEN_HOME="/opt/apache-maven-3.8.6/bin"
						"$MAVEN_HOME/mvn" --version
						'''	
					}
				}
				
			}
			
		}
		stage ('Creation de fichier exemple') {
			steps {
				sh 'touch exemple.txt'
				sh 'echo "Exemple d\'un pipeline" >> exemple.txt'
			}
		}	
	}
}
