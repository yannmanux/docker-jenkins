pipeline {
    agent any 
     environment {
     stages {
         stage ('build the image') {
            steps {
              sh ' docker build -t yannmanux/imagemanu4 .'
            }
         }
     }
}