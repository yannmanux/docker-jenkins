pipeline {
    agent any 
     stages {
         stage ('build the image') {
            steps {
              sh ' docker build -t yannmanux/imagemanu4 .'
            }
         }
     }
}