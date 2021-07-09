pipeline{
    agent any
    tools {nodejs "nodejs"}
    stages{
	    stage('install'){
		steps{
		 sh "cd ${WORKSPACE}"
	     sh "npm install"
	     sh "npm run ng build --prod"
	     sh "aws s3 cp dist/my-first-project s3://naman-070721211/ --recursive"
	}
	}
}
post {
    success {
        emailext body: 'Build is passed', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Successfull execution of pipeline'

    }
    failure {
        emailext body: 'Build is failed', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Failure of pipeline'

    }
    unstable {
        emailext body: 'Unstable build', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Unstable build'
    }
    changed {
        emailext body: 'State of pipeline changed', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Change in stste of pipeline'
    }
}

}
