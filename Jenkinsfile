pipeline {
	agent any
	stages {
		stage ('Version Maven') {
			steps {
				script {
					echo "${env.BRANCH_NAME}"
					if (env.BRANCH_NAME == 'develop') {
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
