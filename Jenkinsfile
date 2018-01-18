pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'mvn install'
            }
        }
    }
    agent {label 'pipe_test'}
    stages {
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
    agent {label 'pipe_skiptest'}
    stages {
        stage('Skip test') {
            steps {
                sh 'mvn install -Dmaven.test.skip=true'
            }
        }
    }
}
