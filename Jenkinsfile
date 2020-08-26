pipeline {
  agent any

  tools {
    node "NodeJS"
  }

  stages {
    stage('build') {
      steps {
        sh "npm install"
        sh "npm run build"
      }
    }

    stage('deploy') {
      steps {
        echo "ng deploy --base-href=/gestion-des-absences-front/"
      }
    }
  }
}
