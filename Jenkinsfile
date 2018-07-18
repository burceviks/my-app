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
  
}
