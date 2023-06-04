pipeline {
  agent { label 'master' }
  tools { maven "3.6.3" }
  stages {
    stage("Build Image") {
       stages {
          stage("clean"){
            steps {
              sh "mvn clean package"
            }
          }
       }     
    }
  }
}
