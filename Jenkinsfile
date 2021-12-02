pipeline {
    agent any
    stages {
        stage('Git Clone') {
            steps {
                git 'https://github.com/submah/maven-helloworld.git'
            }
            
        }
        stage('Maven Build') {
            steps {
                sh 'mvn clean package deploy' 
            }
            
        }
        stage('Deploying to Tomcat') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'jenkins', path: '', url: 'http://34.125.110.229:8080')], contextPath: 'devops123', war: '**/*.war'
            }
            
        }
        
    }
    
}
