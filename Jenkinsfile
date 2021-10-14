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
                deploy adapters: [tomcat7(credentialsId: '1ca6f74a-23f4-4c92-8ad7-fa44e2bbbae9', path: '', url: 'http://ec2-18-191-237-212.us-east-2.compute.amazonaws.com:8080/')], contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
        }
    }
}
