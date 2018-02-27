pipeline {
  agent any
  stages {
    stage('Stage1') {
      parallel {
        stage('Stage1') {
          agent {
            node {
              label 'master'
            }
            
          }
          steps {
            echo 'Blue Pipeline Step 1'
          }
        }
        stage('Stage2') {
          agent {
            node {
              label 'slave1'
            }
            
          }
          steps {
            archiveArtifacts(artifacts: '**/target/*', fingerprint: true)
            junit '**/target/surefire-reports/TEST-*.xml'
          }
        }
      }
    }
  }
}