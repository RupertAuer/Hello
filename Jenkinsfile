pipeline {
  agent {
    docker {
      image 'docker'
    }

  }
  stages {
    stage('Hello!') {
      agent {
        docker {
          image 'microsoft/dotnet'
        }

      }
      steps {
        sh 'dotnet new console'
      }
    }
  }
}