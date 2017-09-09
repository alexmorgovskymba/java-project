pipeline {
  agent any

  environment {
	MYVAR = 5
  }

  stages {
    stage('build') {
      steps {
        sh 'ant -f build.xml -v'
	archiveArtifacts artifacts: '**/dist/*.jar', fingerprint: true
      }
    }
    stage('test') {
      steps {
        sh 'ant -f build.xml test -v'
	echo $MYVAR
      }
    }
  }

  post {
    always {
      junit 'TEST-*.xml'
    } 
  }
}
