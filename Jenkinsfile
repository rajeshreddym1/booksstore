pipeline {
  agent any

  stages {
    stage("git_checkout") {
      steps {
        echo "Cloning repository"
        // Add your Git clone steps here
        // For example: git branch: 'master', url: 'https://github.com/example/repository.git'
        echo "Repository cloned successfully"
      }
    }

    stage("Maven Test") {
      steps {
        echo "Running Maven tests"
        // Add your Maven test steps here
        // For example: sh 'mvn test'
      }
    }

    stage("SonarQube Analysis") {
      steps {
        echo "Running SonarQube analysis"
        // Execute SonarQube analysis with Maven
        sh 'mvn clean verify sonar:sonar \
          -Dsonar.projectKey=github-project \
          -Dsonar.projectName=\'github-project\' \
          -Dsonar.host.url=http://192.168.33.10:9001 \
          -Dsonar.login=sqp_f9c83e0f61e6e72fa7cb77d6faf68476d3cffc30'
      }
    }

    stage("Maven Build") {
      steps {
        echo "Running Maven build"
        // Add your Maven build steps here
        // For example: sh 'mvn package'
      }
    }
  }
}
