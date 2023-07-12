pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr:'5'))
    disableConcurrentBuilds()
    timestamps()
    timeout(time: 60, unit: 'MINUTES')
  }
  stages {
    stage("Checkout") {
      steps {
        checkout scmGit(
    branches: [[name: '*/master']],
    extensions: [pruneStaleBranch(), pruneTags(true)],
    userRemoteConfigs: [[url: 'https://github.com/durgamaheshk/jenkinspipeline_demo.git']])
      }
    }
  }
}