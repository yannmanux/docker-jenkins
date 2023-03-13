pipeline {
    agent any 
     stages {
        stage ('check docker version') {
            steps {
                sh ' docker --version'
            }
        }
        stage ('check java version') {
            steps {
                sh 'java --version'
            }
        }
         stage ('build the image') {
            steps {
              sh ' docker build -t yannmanux/imagemanu4 .'
            }
         }
     }
}