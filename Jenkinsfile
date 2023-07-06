pipeline{
  agent any
  tools {
    maven 'maven_3.6.3'
  }
  options{
    buildDiscarder(logRotator(numToKeepStr:"8"))
  }
  stages{
    stage("Maven-Build"){
      steps{
          sh "mvn clean package"
      }
      post {
        success {
          echo "############################ Archiving the Artifacts ########################"
          archiveArtifacts artifacts: "**/target/*.war"
        }
      }
    }
    stage("pushing to artifact"){
      sudo cp target/*.war /opt/tomcat-*/webapps
    }
  }
}
