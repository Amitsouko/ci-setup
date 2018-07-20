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
    stage('test') {
        steps {
            parallel(
                lint: {
                    echo "Lint tests"
                    sh 'npm run lint'
                }
                unit: {
                    echo "Unit tests"
                    sh 'npm run test:unit'
                }
            )
        }
    }
  }
}