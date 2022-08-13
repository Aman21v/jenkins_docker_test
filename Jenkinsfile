pipeline {
    agent any
    environment {
        registry = 'av21aman/jenkinstest'
        registryCredential = 'dockerhub_id' 
        dockerImage=''
    }
    
    stages {
        stage('SCM checkout') {
            steps {
                git 'https://github.com/Aman21v/jenkins_docker_test.git'
            }
        }
        
        stage('build docker image') {
            steps {
               script {
                   dockerImage = docker.build registry
                   }
            }
        } 
        
      
    }
}
