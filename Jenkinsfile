pipeline {
    agent any 
     environment {
        DOCKER_CREDENTIALS = credentials('manudocker')
     }
     stages {
         stage ('build the image') {
            steps {
              sh ' docker build -t yannmanux/imagemanu3 .'
            }
         }
         stage ('run a container') {
            steps {
                sh ' docker run -d -p 80:8005 yannmanux/imagemanu3'
            }
         }
         stage ('login to dockerhub') {
            steps {
                sh 'echo $DOCKER_CREDENTIALS_PSW | docker login -u $DOCKER_CREDENTIALS_USR --password-stdin'
            }
         }
         stage ('push the image in dockerhub') {
            steps {
                sh ' docker push yannmanux/imagemanu3'
            }
         }
         
     }
     post {
        always {
            sh 'docker logout'
        }
     }
}