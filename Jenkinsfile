pipeline {
    agent any 
     environment {
        DOCKER_CREDENTIALS = credentials('Yannick-Dockerhub')
     }
     stages {
         stage ('build the image') {
            steps {
              sh ' docker build -t imagemanu .'
            }
         }
         stage ('login to dockerhub') {
            steps {
                sh 'docker login -u $dockerUsername -p $dockerPassword'
            }
         }
         stage ('push the image in dockerhub') {
            steps {
                sh ' docker push imagemanu'
            }
         }
         
     }
     post {
        always {
            sh 'docker logout'
        }
     }
}