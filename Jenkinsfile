pipeline {
  agent {
    docker {
      image 'node:8'
    }

  }
  stages {
    stage('build') {
      steps {
        echo "Branch is ${env.BRANCH_NAME}..."
        echo "Performing npm build..."
        sh 'npm install'
      }
    }
  }
}