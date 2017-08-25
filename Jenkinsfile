pipeline {
  agent any

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
        
  }

  post {
    always {
      junit 'TEST-*.xml'
    } 
  }
}
