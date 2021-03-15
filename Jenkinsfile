pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/surajshinde3/jenkins.git'
            }
        }
        
        stage('Build'){
            steps{
                bat 'mvn package'
            }
        }
        
        stage('Deploy'){
            steps{
                deploy adapters: [tomcat8(credentialsId: 'tomcat-cred', path: '', url: 'http://localhost:8060/')], contextPath: 'servlet-jsp', war: '*/.war'
            }
        }
        
    }
}
