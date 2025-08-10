pipeline {
  agent { label 'linux' }
  tools {
    maven '3.9.11'
  }
  stages {
    stage('run test') {
      steps {
        sh 'mvn clean verify'
      }
    }
  }
  post {
    success {
      archiveArtifacts artifacts: 'target/jmeter/**/*.log, target/jmeter/**/*.csv', followSymlinks: false
    }
  }
}
