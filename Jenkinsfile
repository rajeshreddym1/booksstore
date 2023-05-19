pipeline {
  agent any
  
  stages {
    stage('Checkout') {
      steps {
        // Checkout code from Git repository
        git main: 'bookstore', url: 'https://github.com/rajeshreddym1/bookstore.git'
      }
    }
    
    stage('Maven Test') {
      steps {
        // Run Maven tests
        sh 'mvn test'
      }
    }
    
    stage('Maven Build') {
      steps {
        // Run Maven build
        sh 'mvn package'
      }
    }
  }
}
