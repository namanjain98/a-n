pipeline{
      agent { docker { image 'node:14-alpine' } }

    stages{
	
	stage('install'){
		steps{
		   sh "cd ${WORKSPACE}"
	     sh "npm install"
	     sh "npm run ng build --prod"
	     sh "aws s3 cp dist/angular-app-aws s3://naman-07072121/ --recursive"
	}
	}
}
}

