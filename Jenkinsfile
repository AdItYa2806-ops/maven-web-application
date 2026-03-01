node {

def mavenHome = tool name: 'maven3.9.8' 

properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), pipelineTriggers([pollSCM('* * * * *')])])

stage('CheckOutCode'){
git branch: 'development', credentialsId: 'eb319263-3f62-435d-ab8a-69d0a0b98f44', url: 'https://github.com/AdItYa2806-ops/maven-web-application.git'
}

stage('Build'){
sh "${mavenHome}/bin/mvn clean package"
}

/*
stage('ExecuteSonarQubeReport'){
sh "${mavenHome}/bin/mvn clean sonar:sonar" 
}

stage('UploadArtifactsIntoNexus'){
sh "${mavenHome}/bin/mvn clean deploy"
}

stage('DeployAppintoTomcatServer'){
sshagent(['6188566f-c0e5-4380-9d8b-ebedcd8bad9f']) {
sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@172.31.4.210:/opt/apache-tomcat-9.0.113/webapps"
}
}
*/
}
