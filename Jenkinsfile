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
                deploy adapters: [tomcat7(credentialsId: '2a80bb8d-9dcb-4901-9f78-7d8ab4c41bbd', path: '', url: 'http://ec2-18-191-237-212.us-east-2.compute.amazonaws.com:8080/')], contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
        }
    }
}
