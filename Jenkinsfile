pipeline {
    agent any
    environment {
        dockerImage=''
        rg= 'av21aman/jenkinstest'
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
                   dockerImage = docker.build rg
                   }
            }
        } 
        
      
    }
}
