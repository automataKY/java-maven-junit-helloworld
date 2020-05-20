pipeline {
  agent any
  stages {
    stage('checkout project') {
      steps {
        checkout scm
      }
    }

    stage('sh') {
      steps {
        sh 'mvn -Dmaven.test.failure.ignore=true clean package'
        archiveArtifacts 'target/*.jar'
      }
    }

    stage('test') {
      steps {
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }

  }
}