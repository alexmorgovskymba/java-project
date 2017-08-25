pipeline {
  agent any

  stages {
    stage('build') {
      steps {
        sh 'ant -f build.xml -v'
	archiveArtifacts artifacts: '**/dist/*.jar', fingerprint: true
      }
    }
  }

  post {
    always {
      archive 'dist/*.jar'
    } 
  }
}
