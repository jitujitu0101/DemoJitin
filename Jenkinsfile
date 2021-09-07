pipeline {
    agent any
	tools {
		maven '3.8.2'
	}
	
	stages {
        stage('Test Stage 1') {
            steps {
               bat 'mvn --version'
            }
        }
    
        stage('Build') {
            steps {
               bat 'mvn -B -DskipTests clean package'
            }
        }
    }
}