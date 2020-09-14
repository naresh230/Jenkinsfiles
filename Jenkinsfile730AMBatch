node
{
 
  def mavenHome = tool name: "maven3.6.3" 
  
      // echo "GitHub BranhName ${env.BRANCH_NAME}"
      // echo "Jenkins Job Number ${env.BUILD_NUMBER}"
      // echo "Jenkins Node Name ${env.NODE_NAME}"
  
       echo "Jenkins Home ${env.JENKINS_HOME}"
       echo "Jenkins URL ${env.JENKINS_URL}"
       echo "JOB Name ${env.JOB_NAME}"
 
  
  properties([[$class: 'JiraProjectProperty'], buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), pipelineTriggers([pollSCM('* * * * *')])])
  
 stage('CheckoutCode')
 {
  git branch: 'development', credentialsId: '7fbdf410-f577-4c3f-8841-f8d887938ce4', url: 'https://github.com/MithunTechnologiesDevOps/maven-web-application.git'
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
 
 stage('UploadArtifactIntoNexus')
 {
 sh "${mavenHome}/bin/mvn deploy"
 }
 
 stage('DeployAppintoTomcatServer')
 {
 sshagent(['47288ceb-add0-4fb2-885d-89fb8b9ee419']) 
 {
    sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@3.16.37.124:/opt/tomcat9/webapps/"
 }
 }

  stage('SendEmailNotification')
 {
 mail bcc: 'devopstrainingblr@gmail.com', body: '''Build is over..

 Regards,
 Mithun Technologies,
 9980923226.''', cc: 'devopstrainingblr@gmail.com', from: '', replyTo: '', subject: 'Build is over', to: 'devopstrainingblr@gmail.com'
 }
*/
 
}
