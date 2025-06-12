pipeline {
	agent any
	
	tools {
		maven 'Maven 3.9.9'
		jdk 'JDK24'
	}
	
	stages {
		stage('Clonar') {
			steps {
                git url: 'https://github.com/fahg-cl/SaludoApp.git', branch: 'main'
			}
	}
		
		stage('Compilar') {
			steps {
				bat 'mvn clean compile'
				}
			}

		stage('Probar') {
			steps {
				bat 'mvn test'
				}
			}

		stage('Empaquetar') {
			steps {
				bat 'mvn package'
				}
			}
		}	
		post {
			success {
				echo "🎉 El build fue exitoso al fin!"
				}
			failure {
				echo "💥 El build falló"
				}
			}
		}		