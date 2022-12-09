pipeline {
	agent any
	parameters {
		string(name: 'BRANCH', defaultValue: 'master', description: 'Name of the branche to use.')
		choice(name:'ENVIRONMENT' , choices: ['int','ap','op'])
	}
	stages {
		stage ('Version Maven') {
			steps {
				script {
					echo "${params.BRANCH}"
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
		stage ('Deploy app') {
			when {
				expression { params.ENVIRONMENT == 'op' }	
			}
			steps {
				sh 'echo "Deploy APP"'
			}
		}
		stage ('Test') {
			agent {
				docker { image 'node:16.13.1-alpine' }	
			}
			steps {
				sh 'node --version'
			}
		}
	}
}
