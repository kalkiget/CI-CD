pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        sh 'mvn -B test package'
      }
    }

    stage('Deploy') {
      when { branch 'main' }
      steps {
        sh 'kubectl apply -f k8s/'
      }
    }
  }
}
