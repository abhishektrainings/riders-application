node
 {
  
  def mavenHome = tool name: "maven3.8.8"
  
      echo "GitHub BranhName ${env.BRANCH_NAME}"
      echo "Jenkins Job Number ${env.BUILD_NUMBER}"
      echo "Jenkins Node Name ${env.NODE_NAME}"
  
      echo "Jenkins Home ${env.JENKINS_HOME}"
      echo "Jenkins URL ${env.JENKINS_URL}"
      echo "JOB Name ${env.JOB_NAME}"
  
   properties([[$class: 'JiraProjectProperty'], buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '2', daysToKeepStr: '', numToKeepStr: '2')), pipelineTriggers([pollSCM('* * * * *')])])
  
  stage("CheckOutCodeGit")
  {
   git branch: 'master', credentialsId: 'none', url: 'https://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@github.com/abhishektrainings/riders-application.git'
 }
 
 stage("Build")
 {
 sh "${mavenHome}/bin/mvn clean package"
 }
 
  /*
 stage("ExecuteSonarQubeReport")
 {
 sh "${mavenHome}/bin/mvn sonar:sonar"
 }
 
 stage("UploadArtifactsintoNexus")
 {
 sh "${mavenHome}/bin/mvn deploy"
 }
 
  stage("DeployAppTomcat")
 {
  sshagent(['423b5b58-c0a3-42aa-af6e-f0affe1bad0c']) {
    sh "scp -o StrictHostKeyChecking=no target/riders-application.war  azureuser@15.206.91.239:/opt/tomcat/webapps/" 
  }
 }
 
 stage('EmailNotification')
 {
 mail bcc: 'abhishektrainings30@gmail.com', body: '''Build is over

 Thanks,
 Abhishek Trainings,
 8818877113.''', cc: 'abhishektrainings30@gmail.com', from: '', replyTo: '', subject: 'Build is over!!', to: 'abhishektrainings30@gmail.com'
 }
 */
 
 }
