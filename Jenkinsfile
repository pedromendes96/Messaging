pipeline {
  agent {
    docker {
      image 'openjdk:11'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh './gradlew build'
      }
    }

    stage('Unit test') {
      steps {
        sh './gradlew test'
      }
    }

    stage('Integration tests') {
      steps {
        sh './gradlew integrationTest'
      }
    }

  }
}