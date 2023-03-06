pipeline {
    agent any 
     environment {
        DOCKER_CREDENTIALS = credentials('Yannick-dockerhub')
     }
     stages {
         stage ('build the image') {
            steps {
              sh ' docker build -t imagemanu .'
            }
         }
         stage ('login to dockerhub') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
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