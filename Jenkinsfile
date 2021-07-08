pipeline {
  agent any
  stages {
    stage('Install') {
      steps { sh '#!/usr/bin/env bash'
	      sh 'cd ${WORKSPACE}'
              sh 'npm install'
              sh 'ng build --prod'
              sh 'aws s3 cp dist/angular-app-aws s3://naman-07072121/ --recursive'
	 }
    }
}
}
