pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'this is the build the step of the pipeline'
        sh 'mvn compile'
      }
    }

    stage('test') {
      steps {
        echo 'this is the test step of the pipeline'
        sh 'mvn clean test'
      }
    }

    stage('package') {
      steps {
        echo 'this is the packaging step of the pipeline'
        sh 'mvn package -DskipTests'
      }
    }

    stage('ArchiveFiles') {
      steps {
        archiveArtifacts '**/target/*.jar'
      }
    }

  }
  tools {
    maven 'maven'
  }
  post {
    always {
      echo 'this pipeline has completed...'
    }

  }
}