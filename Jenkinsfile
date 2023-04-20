pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/BParent777/flask', branch: 'main')
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -t bparent777/flask_app .'
      }
    }

    stage('Docker Login') {
      steps {
        sh 'docker login -u bparent777 -p dckr_pat_nzxbJud1oUvUyOjo5bVsuWdp8Ss'
      }
    }

    stage('Docker Push') {
      steps {
        sh 'docker push bparent777/flask_app'
      }
    }

  }
}