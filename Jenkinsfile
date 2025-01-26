pipeline { // this is a nice feature
    agent any
    tools {
       maven 'maven399'
    }
    parameters { string(name: 'maven_command', defaultValue: 'install', description: 'maven command to run in the first stage') }
    stages {
        // stage('Source') {
            
        //     steps {
        //         script{
        //         git branch: 'main', poll: false, url: 'https://github.com/spring-projects/spring-petclinic.git'
        //     }}
        // }
        stage('mvn command'){
            steps {
                sh "mvn ${params.maven_command}"
            }
        }
        
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