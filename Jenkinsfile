pipeline {
    agent none
    stages {
        stage('Build') {
            agent any
            steps {
                sh 'mvn install'
            }
        }
        stage('Test') {
            agent { label 'pipe_test' }
            steps {
                sh 'mvn test'
            }
        }
        stage('Skip test') {
            agent { label 'pipe_skiptest' }
            steps {
                sh 'mvn install -Dmaven.test.skip=true'
            }
        }
    }
}
