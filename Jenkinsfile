pipeline {
  agent any
  stages {
    stage('Echo Version') {
      steps {
        sh 'echo Print Maven Version'
        sh 'mvn -version'
      }
    }

    stage('Build') {
      steps {
        git(branch: 'main', url: 'https://github.com/OrgYT/Jenkins-repo1.git')
        sh 'mvn clean package -DskipTests=true'
        archiveArtifacts 'target/hello-world.*.jar'
      }
    }

    stage('Unit Test') {
      steps {
        sh 'mvn test'
      }
    }

  }
  tools {
    maven 'M398'
  }
}