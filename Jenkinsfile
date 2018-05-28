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
    stage('error') {
      steps {
        emailext(subject: '[JENKINS][$PROJECT_DISPLAY_NAME][$BUILD_STATUS]', body: '${SCRIPT, template="groovy-html.template"}', mimeType: 'text/html', to: 'r.auer@reply.de', replyTo: '$DEFAULT_REPLYTO')
      }
    }
  }
}