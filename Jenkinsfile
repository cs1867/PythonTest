pipeline {
  agent any
  stages {
    stage('Checkout Code') {
      steps {
        git(url: 'https://github.com/cs1867/PythonTest.git', branch: 'main')
      }
    }

    stage('Script Check') {
      steps {
        sh 'ls -al '
      }
    }

    stage('Python Script') {
      steps {
        sh 'python3 MOD.py'
      }
    }

  }
}