pipeline {
    agent any
    environment {
        registryCredential = 'dockerhub_id' 
    }
    stages {
        stage('SCM checkout') {
            steps {
                git 'https://github.com/Aman21v/jenkins_docker_test.git'
            }
        }
        
        stage('build docker image') {
            steps {
                sh 'docker build -t av21aman/jenkinstest:$BUILD_NUMBER .'
            }
        } 
        
      
    }
}
