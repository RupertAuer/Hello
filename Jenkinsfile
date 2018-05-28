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
  post {
    success {
      emailext(postsendScript: '$DEFAULT_POSTSEND_SCRIPT', body: '${SCRIPT, template="groovy-html.template"}', presendScript: '$DEFAULT_PRESEND_SCRIPT', mimeType: 'text/html', subject: '[JENKINS][$PROJECT_DISPLAY_NAME][$BUILD_STATUS]', to: 'r.auer@reply.de, r.auer@clusterreply.com', replyTo: '$DEFAULT_REPLYTO')

    }

    failure {
      emailext(postsendScript: '$DEFAULT_POSTSEND_SCRIPT', body: '${SCRIPT, template="groovy-html.template"}', presendScript: '$DEFAULT_PRESEND_SCRIPT', mimeType: 'text/html', subject: '[JENKINS][$PROJECT_DISPLAY_NAME][$BUILD_STATUS]', to: 'r.auer@reply.de, r.auer@clusterreply.com', replyTo: '$DEFAULT_REPLYTO', recipientProviders: [[$class: 'DeveloperRecipientProvider']])

    }

  }
}