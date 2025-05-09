pipeline {
    agent any
    stages {
        stage('Build') { 
            steps {
                dir('my-app') {
                    sh 'mvn -B -DskipTests clean package'
                }
            }
        }
		stage('Test') {
            steps {
				dir('my-app') {
					sh 'mvn test'
				}
			}
            post {
                always {
					dir('my-app') {
						junit 'target/surefire-reports/*.xml'
					}
				}
            }
        }
		stage('Deliver') { 
            steps {
                sh './jenkins/scripts/deliver.sh' 
            }
        }
    }
}