pipeline {
  agent { label 'linux' }
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
