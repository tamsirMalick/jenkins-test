pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        bat 'gradlew assembleDebug'
      }
    }

    stage('mobsf scan') {
      steps {
        bat 'gradlew scan'
      }
    }

    stage('mobsf check-status') {
      steps {
        bat 'gradlew checkStatus'
      }
    }

    stage('mobsf getReport') {
      steps {
        bat 'gradlew getReport'
      }
    }

  }
  
  post {
    always {
      archiveArtifacts artifacts: 'target/build/outputs/mobsf/*.pdf'
    }
  }
  tools {
    gradle 'gradle66'
  }
}
