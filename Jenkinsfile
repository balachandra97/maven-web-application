node
{
 
 def mavenHome = tool name: "maven 3.8.1"

 stage('checkout code')
 {
 git branch: 'development', credentialsId: 'cdee5d28-b2a6-446e-985e-3a56e9a7f038', url: 'https://github.com/balachandra97/maven-web-application.git'
 }

 stage('Build')
 {
 sh "${mavenHome}/bin/mvn clean package"
 }
 /* 
 stage('ExecuteSonarQubeReport')
 {
 sh "${mavenHome}/bin/mvn sonar:sonar"
 }

 stage('UploadArtifactsintoNexus')
 {
 sh "${mavenHome}/bin/mvn deploy"
 }
 
 stage('DeployAppintoTomcatServer')
 {
 sshagent(['bcb7d898-1f7c-4742-b4ad-88b6740317b6']) {
 sh "scp -o StrictHostKeyChecking=No target/maven-web-application.war ec2-user@3.110.119.110:/opt/apache-tomcat-9.0.70/webapps/"
 }
 }
  */
 stage('SendEmailNotification')
 {
 emailext body: '''build over..

 regards,
 reddybalachandra,
 9550390740''', subject: 'build over..', to: 'reddybalachandra9740@gmail.com'
 }
 
}
