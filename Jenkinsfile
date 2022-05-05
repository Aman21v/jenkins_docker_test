  pipeline {
environment {
registry = "av21aman/aman_21"
registryCredential = 'docker_hub'
dockerImage = ''
}
agent any
stages {
stage('Cloning our Git')
   {
      checkout scm  
   }
  
stage('Building our image') {
steps{
script {
dockerImage = docker.build(registry + ":$BUILD_NUMBER")
}
}
}
stage('Deploy our image') {
steps{
script {
docker.withRegistry( '', registryCredential ) {
dockerImage.push()
}
}
}
}

