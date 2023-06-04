pipeline {
  agent { label 'master' }
  tools { maven "3.6.3" }
  stages {
    stage("Build Image") {
       stages {
       
          stage("clean package"){
            steps {
              sh "mvn clean package"
            }
          }
          
          stage("Build Images"){
            steps {
              sh "docker build -t PhirakbotDiff/kube-register:1.1.1 ."
            }
          }
          
          stage("Docker login && Push to Images"){
            steps {
              withCredentials([usernamePassword(credentialsId: 'dockerhub', passwordVariable: 'password', usernameVariable: 'username')]) {
                  sudo docker login --username usernameVariable --password-stdin passwordVariable
              }
            }
          }
          
          stage("Ansible"){
            steps {
              sh """
              
              """
            }
          }
         
       }     
    }
  }
}
