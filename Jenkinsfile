node {
   stage('SCM Checkout'){
 git 'https://github.com/bingoassistance/my-app'
 }
 stage('Compile-Package'){
          def mvnHome= tool name: 'maven', type: 'maven'
    sh "${mvnHome}/bin/mvn package"
  }
 
}
stage('Email Notification'){
		mail bcc: '', body: """Hi Team, You build successfully deployed
		                       Job URL : ${env.JOB_URL}
							   Job Name: ${env.JOB_NAME}
Thanks,
DevOps Team""", cc: '', from: '', replyTo: '', subject: "${env.JOB_NAME} Success", to: 'golinux4@gmail.com'
   
   }
}
