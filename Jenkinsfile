pipeline {
	agent any
	
	tools {
		maven 'Maven 3.9.9'
		jdk 'JDK24'
	}
	
	stages {
		stage('Clonar') {
			steps {
				git url:'https://github.com/fahg-cl/SaludoApp.git'
			}
	}
		
		stage('Compilar') {
			steps {
				sh 'mvn clean compile'
				}
			}

		stage('Probar') {
			steps {
				sh 'mvn test'
				}
			}

		stage('Empaquetar') {
			steps {
				sh 'mvn package'
				}
			}
		}	
		post {
			success {
				echo "🎉 El build fue exitoso"
				}
			failure {
				echo "💥 El build falló"
				}
			}
		}		