pipeline {
  agent any
  stages {
    stage('test'){
      steps{
        sh 'echo "hello this is duplicate repo"'
        sh 'echo "${BRANCH}"'
      }
    }
  }
}
