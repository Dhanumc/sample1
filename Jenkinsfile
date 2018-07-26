pipeline {
    agent any
    stages {
        stage('checkout scm') {
            steps {
               checkout scm
            }
        }
        stage('compile stage') {
            steps {
                    sh 'mvn install'
                }
            }
        stage('Testing stage') {
            steps {
                     sh 'mvn test'
                   }
               }
        
        stage('Dewployment stage') {
            steps {
                     sh 'mvn deploy'
                   }
               }    
     }
}
