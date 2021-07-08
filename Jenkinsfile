pipeline {
  agent any
  stages {
    stage('SCM') {
      git branch: 'main', url:'git@github.com:namanjain98/a-n.git'
    }
    stage('install'){
	    sh "cd ${WORKSPACE}"
	    sh "npm install"
	    sh "npm run ng build --prod"
	    sh "aws s3 cp dist/angular-app-aws s3://naman-07072121/ --recursive"
	}	
    
}
}
