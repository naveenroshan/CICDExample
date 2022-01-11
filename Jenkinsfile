pipeline {
    agent any
    stages {
        stage('Build') {
            steps{
                // Run Maven on a Unix agent.
                sh "mvn clean package"
            }
        }
        stage('Deploy') {
            steps{            
                deploy adapters: [tomcat7(credentialsId: 'a7df8180-be4a-45d7-93ad-548bd6fff0d1', path: '', 
                url: 'https://ec2-18-118-149-105.us-east-2.compute.amazonaws.com:8080/')], 
                contextPath: 'worldtime', war: '**/*.war'
            }
        }
    }
}
