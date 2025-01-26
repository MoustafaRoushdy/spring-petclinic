pipeline {
    agent any
    tools {
       maven 'maven399'
    }
    when {
        branch "feature/*"
    }
    stages {
        stage('Source') {
            
            steps {
                script{
                git branch: 'main', poll: false, url: 'https://github.com/spring-projects/spring-petclinic.git'
            }}
        }
        
        stage('Package'){
            steps {
                sh "mvn package"
            }
        }
        
        stage('Test'){
            steps {
                sh "mvn test"
            }
        }
    }
}