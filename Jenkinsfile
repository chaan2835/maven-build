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
    stage("push to tomcat"){
	    steps{
		    sshagent(['tomcat-user']) {
  			  sh "scp -o StrictHostKeyChecking=no target/*.war ubuntu@13.233.247.30:/opt/tomcat-10/webapps"
	        }
        }
    }
  }
}
