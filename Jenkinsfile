pipeline{
  agent any
  options{
    buildDiscarder(logRotator(numToKeepStr:"2"))
  }
  stages{
    stage("Maven-Build"){
      steps{
          sh "mvn clean package"
      }
    }
  }
}
