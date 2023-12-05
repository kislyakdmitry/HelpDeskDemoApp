pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'chmod +x ./gradlew'
        sh './gradlew clean build'
      }
    }
    stage('deploy to maven local') {
      steps {
        sh 'chmod +x ./gradlew'
        sh './gradlew publishToMavenLocal'
      }
    }
  }
  tools {
    jdk 'JDK_17_new'
  }
}
