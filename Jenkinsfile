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
	}
}