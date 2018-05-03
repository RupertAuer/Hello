pipeline {
  agent {
    docker {
      image 'microsoft/dotnet'
    }

  }
  stages {
    stage('') {
      steps {
        sh 'dotnet new console'
        sh 'dotnet run'
      }
    }
  }
}