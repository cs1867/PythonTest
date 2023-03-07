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
            sh 'ls -al '
          }
        }

        stage('Send mail') {
          steps {
            mail(subject: 'test', body: 'Jenkins test pass', from: 'csacco@iu.edu', to: 'csacco@iu.edu')
          }
        }

      }
    }

    stage('Python Script') {
      steps {
        sh 'python3 MOD.py'
      }
    }

    stage('log in docker hub') {
      environment {
        DH_USERNAME = 'cs1867'
        DH_PWD = 'Jeep1979!!'
      }
      steps {
        sh ''' 

ls -al '''
      }
    }

    stage('Push container') {
      steps {
        sh '''docker push cs1867/jenkinstest1:latest
'''
      }
    }

  }
}