pipeline {
    agent any 
     environment {
        DOCKER_CREDENTIALS = credentials('Yannick-dockerhub')
     }
     stages {
         stage ('build the image') {
            steps {
              sh ' docker build -t yannmanux/imagemanu .'
            }
         }
         stage ('login to dockerhub') {
            steps {
                sh 'echo dckr_pat_zl_874si9-yA2vU_e-Yn5kV6wx8 | docker login -u yannmanux --password-stdin'
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