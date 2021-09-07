pipeline {
    agent any
	tools {
		maven '3.8.2'
	}
	
	stages {
        stage('Test Stage 1') {
            steps {
               sh 'mvn --version'
            }
        }
    
        stage('Build') {
            steps {
               sh 'mvn -B -DskipTests clean package'
            }
        }
    }
}