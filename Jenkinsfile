pipeline {
  agent any
  stages {
    stage('Build') {
      agent {
        docker {
          image 'python:2-alpine'
        }

      }
      environment {
        PythonBuild = '1'
      }
      steps {
        sh 'echo "Building..."'
        sh 'python -m py_compile sources/add2vals.py sources/calc.py'
        stash(name: 'Compile-Results', includes: 'sources/*.py*')
      }
    }

    stage('Test') {
      steps {
        sh 'echo "Testing.."'
      }
    }

    stage('Secure') {
      steps {
        sh 'echo "Securing..."'
      }
    }

    stage('Deploy') {
      steps {
        sh 'echo "Deploying..."'
      }
    }

  }
}