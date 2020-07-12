pipeline {
	agent any
	stages {
		stage ('Compile') {
			steps {
				withMaven(maven : 'Maven_3_6_3') {
					sh 'mvn clean compile'
				}
			}
		}
		stage('Build image') {
          app = docker.build("[id-of-your-project-as-in-google-url]/[name-of-the-artifact]")
        }
        stage('Push image') {
          docker.withRegistry('https://eu.gcr.io', 'gcr:[credentials-id]') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
          }
        }
	}
}