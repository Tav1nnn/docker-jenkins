pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'docker-compose up --build -d'
      }
    }
    stage('Test') {
      steps {
        sh 'docker-compose exec app pytest'
      }
    }
    stage('Deploy') {
      steps {
        sh 'docker-compose up -d'
      }
    }
  }
  post {
    always {
      sh 'docker-compose down'
    }
  }
}
