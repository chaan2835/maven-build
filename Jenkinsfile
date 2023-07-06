pipeline{
  agent any
  tools {
    maven 'Maven_3.6.3'
  }
  options{
    buildDiscarder(logRotator(numToKeepStr:"8"))
  }
  stages{
    stage("Maven-Build"){
      steps{
          sh "mvn clean package"
      }
    }
  }
}
