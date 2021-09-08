pipeline {
    agent {label 'SlaveNode1'}
	triggers {
		pollSCM('')
	}
	tools {
		maven '3.8.2'
	}
   
        stage('Build') {
            steps {
               bat 'mvn -B -DskipTests clean package'
            }
        }
		
		stage('Testing') { 
            steps {
                bat 'mvn test' 
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml' 
                }
			
            }
        }
		
		stage('End to CI') {
            steps {
                echo 'This comes to an end of CI pipeline.' 
            }
        }
    }
}