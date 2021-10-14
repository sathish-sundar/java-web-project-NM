pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                sh "mvn clean package"
            }
        }
        stage('Deploy'){
            steps{
                deploy adapters: [tomcat7(credentialsId: 'cfcbb2d6-7b1f-4311-ac82-5378f9f1a0d6', path: '', url: 'http://ec2-18-191-237-212.us-east-2.compute.amazonaws.com:8080/')], contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
        }
    }
}
