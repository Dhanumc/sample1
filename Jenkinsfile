pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'mvn install'
            }
        }
        stage('Test') {
            node {label 'pipe_test'}
            steps {
                sh 'mvn test'
            }
        }
        stage('Skip test') {
            node {label 'pipe_skiptest'}
            steps {
                sh 'mvn install -Dmaven.test.skip=true'
            }
        }
    }
}
