pipeline{
      agent any
    tools {nodejs "nodejs"}


    stages{
	
	stage('install'){
		steps{
		   sh "cd ${WORKSPACE}"
	     sh "npm install"
	     sh "npm run ng build --prod"
	     sh "aws s3 cp dist/my-first-project s3://naman-07072121/ --recursive"
	}
	}
}
}

