pipeline {
    agent any 
     stages {
        stage ('check docker version') {
            steps {
                sh ' docker --version'
            }
        }
         stage ('build the image') {
            steps {
              sh ' docker build -t yannmanux/imagemanu4 .'
            }
         }
     }
}