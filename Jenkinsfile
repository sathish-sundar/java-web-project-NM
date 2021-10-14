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
                deploy adapters: [tomcat7(credentialsId: '63244cc0-44ee-4e47-833b-b3ee12ea3c9a', path: '', url: 'http://ec2-18-191-237-212.us-east-2.compute.amazonaws.com:8080/')], contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
        }
    }
}
