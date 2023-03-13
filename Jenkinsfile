pipeline {
    agent any 
     stages {
        stage ('check docker version') {
            steps {
                sh ' docker --version'
            }
        }
        stage ('check maven version') {
            steps {
                sh 'mvn --version'
            }
        }
         stage ('build the image') {
            steps {
              sh ' docker build -t yannmanux/imagemanu4 .'
            }
         }
     }
}