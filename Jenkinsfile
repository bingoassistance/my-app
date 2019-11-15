node {
   stage('SCM Checkout'){
 git 'https://github.com/bingoassistance/my-app'
 }
 stage('Compile-Package'){
          def mvnHome= tool name: 'maven', type: 'maven'
    sh "${mvnHome}/bin/mvn package"
 
}
   stage('Slack-Notification'){
   slackSend baseUrl: 'https://hooks.slack.com/services/', 
      channel: 'jenkins-pipeline-demo', 
      color: 'good', message: 'welcome', 
      tokenCredentialId: 'slack-demo', 
      username: 'devops'
}
}
