pipeline { // this is a nice feature
    agent any
    tools {
       maven 'maven399'
    }
    stages {
        // stage('Source') {
            
        //     steps {
        //         script{
        //         git branch: 'main', poll: false, url: 'https://github.com/spring-projects/spring-petclinic.git'
        //     }}
        // }
        
        stage('Package'){
        when {
                branch "feature/nicefeature"
            }
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