pipeline {
    agent any 
     stages {
        stage ('check docker images') {
            steps {
                sh ' docker images'
            }
        }
         stage ('build the image') {
            steps {
              sh ' docker build -t yannmanux/imagemanu4 .'
            }
         }
     }
}