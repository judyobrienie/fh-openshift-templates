#!groovy

// https://github.com/feedhenry/fh-pipeline-library
@Library('fh-pipeline-library') _

node('nodejs6') {

    stage('Checkout') {
        step([$class: 'WsCleanup'])
        checkout scm
    }

    stage('Lint') {
        sh '''
            npm install jsonlint
            for templatefile in $(ls *.json); do ./node_modules/.bin/jsonlint -q ${templatefile}; done
        '''
    }
}
