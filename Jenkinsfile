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
  tools {
    gradle 'gradle66'
  }
}