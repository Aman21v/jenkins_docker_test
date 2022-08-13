pipeline { 

    environment { 
        registry = "av21aman/jenkinstest" 

        registryCredential = 'dockerhub_id' 

        dockerImage = '' 
    }


    agent any 

    stages { 

        stage('Cloning our Git') { 

            steps { 

                git clone https://github.com/Aman21v/jenkins_docker_test.git

            }

        } 

        stage('Building our image') { 

            steps { 

                script { 

                    dockerImage = docker.build registry + ":$BUILD_NUMBER" 

                }

            } 

        }

        stage('Deploy our image') { 

            steps { 

                script { 

                    docker.withRegistry( '', registryCredential ) { 

                        dockerImage.push() 

                    }

                } 

            }

        stage('Cleaning up') { 
            steps { 
                sh "docker rmi $registry:$BUILD_NUMBER" 
            }
        } 

    }
