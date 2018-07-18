node{
   stage('SCM Checkout'){
     git 'https://github.com/burceviks/my-app'
   }
   stage('Compile-Package'){
      //Get maven home path
     def mvnHome =  tool name: 'maven-3', type: 'maven'
      sh "${mvnHome}/bin/mvn package"
   }
   stage('Email Notification'){
      mail bcc: '', body: '''Hi

Welcome to Jenkins email alerts
Thanks
Burcu''', cc: '', from: '', replyTo: '', subject: 'Jenkins job', to: 'bozcan@gmail.com'

   }
   stage('Slack Notifications')
   {
      slackSend baseUrl: 'https://hooks.slack.com/services/', 
         channel: '#jenkins-pipeline-demo', 
         color: 'good', 
         message: 'Welcome to Jenkins, Slack!', 
         teamDomain: 'mrsagile', 
         tokenCredentialId: 'slack-demo'

   }
  
}
