pipeline {
    agent any
    stages {
        stage('compile stage') {
            steps {
                withMaven(maven: 'maven') {
                    sh 'mvn install'
                }
            }
        }
        stage('Testing stage') {
            steps {
                withMaven(maven : 'maven') {
                     sh 'mvn test'
                   }
               }
        }
        
        stage('Dewployment stage') {
            steps {
                withMaven(maven : 'maven') {
                     sh 'mvn deploy'
                   }
               }
        }
            
    }
}
