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
        branch 'master'
      }
      steps {
        sh 'echo "Publishing"'
      }
    }

    stage('Update infrastructure') {
      when {
        branch 'master'
      }
      steps {
        sh 'echo "Updating infrastructure"'
      }
    }

    stage('Deploy') {
      when {
        branch 'master'
      }
      steps {
        sh 'echo "Deploying"'
      }
    }

  }
}