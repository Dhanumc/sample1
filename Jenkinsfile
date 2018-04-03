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
        
       stage('Publish') {
       nexusPublisher nexusInstanceId: 'NexusRepo123', nexusRepositoryId: 'releases', packages: [[$class: 'MavenPackage', mavenAssetList: [[classifier: '', extension: '', filePath: '/home/advik/.jenkins/workspace/simple_project/target/gamutkart.war']], mavenCoordinate: [artifactId: 'gamutkart', groupId: 'com.gamutgurus', packaging: 'war', version: '1.1']]]
       }   
            
    }
}
