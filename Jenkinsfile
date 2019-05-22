pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'python -m py_compile sources/add2vals.py sources/calc.py'
      }
    }
    stage('Test') {
      steps {
        sh 'py.test --verbose --junit-xml test-reports/results.xml sources/test_calc.py\''
      }
    }
    stage('Deliver') {
      steps {
        sh 'pyinstaller --onefile sources/add2vals.py'
      }
    }
  }
}