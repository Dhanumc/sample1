pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'mvn install'
            }
        }
    }
    node {label 'pipe_test'}
    stages {
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
    node {label 'pipe_skiptest'}
    stages {
        stage('Skip test') {
            steps {
                sh 'mvn install -Dmaven.test.skip=true'
            }
        }
    }
}
