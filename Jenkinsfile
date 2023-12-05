pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'chmod +x ./gradlew'
        sh './gradlew clean build'
      }
    }
    stage('build') {
      steps {
        sh 'chmod +x ./gradlew'
        sh './gradlew publishToMavenLocal'
      }
    }
    stage("Quality Gate") {
      steps {
        timeout(time: 2, unit: 'MINUTES') {
          waitForQualityGate abortPipeline: true
        }
      }
    }
  }
  tools {
    jdk 'JDK_17_new'
  }
}
