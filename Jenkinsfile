pipeline {
  agent {
    node {
      label 'alpine-vm-agent'
    }

  }
  stages {
    stage('Build') {
      steps {
        echo 'Hello from build'
      }
    }

    stage('Test') {
      steps {
        echo 'Testing some stuff'
      }
    }

    stage('Deploy on Testing') {
      parallel {
        stage('Deploy on Testing') {
          steps {
            echo 'Deploying on Testing'
          }
        }

        stage('Deploying on Staging') {
          steps {
            echo 'Deploying on staging'
          }
        }

      }
    }

    stage('Deploy to Prod') {
      steps {
        echo 'Deploying on Prod'
        cleanWs(cleanWhenSuccess: true)
        input(message: 'Continue', ok: 'Yes')
      }
    }

  }
}