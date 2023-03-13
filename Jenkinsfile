pipeline {
  agent any
  stages {
    stage('Checkout Code') {
      steps {
        git(url: 'https://github.com/cs1867/PythonTest.git', branch: 'main')
      }
    }

    stage('Script Check') {
      parallel {
        stage('Script Check') {
          steps {
            sh 'ls -al'
          }
        }

        stage('Send mail') {
          steps {
            mail(subject: 'test', body: 'Jenkins test pass', from: 'csacco@iu.edu', to: 'csacco@iu.edu')
          }
        }

      }
    }

  }
}