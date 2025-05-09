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
    }
}