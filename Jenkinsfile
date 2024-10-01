pipeline {
    agent {
        label "maven"
    }
    tools {
        maven "maven3.9.3"
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }
        stage('Test') {
            steps {

                sh 'mvn test'
            }
        }
        stage('Package') {
            steps {

                sh 'mvn package'
            }
        }
        stage('Storing Artifact') {
            steps {

                archiveArtifacts artifacts: 'target/**/*.jar'
            }
        }
        
    }
}