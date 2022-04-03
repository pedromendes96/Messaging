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

    stage('Publish packages') {
      when {
        branch 'main'
      }
      steps {
        sh 'echo "Publishing"'
      }
    }

    stage('Update infrastructure') {
      when {
        branch 'main'
      }
      steps {
        sh 'echo "Updating infrastructure"'
      }
    }

    stage('Deploy') {
      when {
        branch 'main'
      }
      steps {
        sh 'echo "Deploying"'
      }
    }

  }
}