pipeline {
  agent any

  tools {
    nodejs "NodeJS"
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
        echo "ng deploy --base-href=https://robin-lad.github.io/gestion-des-absences-front/"
      }
    }
  }
  post {

		failure {
			discordSend description: "${BUILD_URL}", footer: 'Echec :( - Robin', image: '', link: '', result: 'FAILURE', thumbnail: '', title: "${env.JOB_NAME}-#${BUILD_NUMBER} - ${env.GIT_COMMIT}", webhookURL: 'https://discordapp.com/api/webhooks/747819422705778738/dHWPHidlNLpiiKftWU84__Ss2LAkws77Swfdk5OWs22qla3hlI1B4zywW8ROg4nAwjRM'
		}

		success {
			script {
				if ("${env.BRANCH_NAME}" == 'master')
					discordSend description: "${BUILD_URL}", footer: 'Success :) - Robin', image: '', link: '', result: 'SUCCESS', thumbnail: '', title: "${env.JOB_NAME}-#${BUILD_NUMBER} - ${env.GIT_COMMIT}", webhookURL: 'https://discordapp.com/api/webhooks/747819422705778738/dHWPHidlNLpiiKftWU84__Ss2LAkws77Swfdk5OWs22qla3hlI1B4zywW8ROg4nAwjRM'
			}
		}
	}
}
