pipeline {
    agent any 
     environment {
        DOCKER_CREDENTIALS = credentials('manudocker')
     }
     stages {
         stage ('build the image') {
            steps {
              sh ' docker build -t yannmanux/imagemanu .'
            }
         }
         stage ('login to dockerhub') {
            steps {
                sh 'echo $DOCKER_CREDENTIALS_PSW | docker login -u $OCKER_CREDENTIALS_USR --password-stdin'
            }
         }
         stage ('push the image in dockerhub') {
            steps {
                sh ' docker push yannmanux/imagemanu'
            }
         }
         
     }
     post {
        always {
            sh 'docker logout'
        }
     }
}