pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'mvn install'
            }
        }
    node {label 'pipe_test'}
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        node {label 'pipe_skiptest'}
        stage('Skip test') {
            steps {
                sh 'mvn install -Dmaven.test.skip=true'
            }
        }
    }
}
