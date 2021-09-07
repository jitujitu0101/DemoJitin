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
		
		stage('Testing') { 
            steps {
                sh 'mvn test' 
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml' 
                }
            }
        }
    }
}