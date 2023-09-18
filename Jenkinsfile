pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Build Completed'
        retry(count: 3) {
          echo 'Trying to build'
        }

      }
    }

    stage('Test stages') {
      parallel {
        stage('Test2') {
          steps {
            echo 'Running test 2'
          }
        }

        stage('Test1') {
          steps {
            echo 'Running Test1'
          }
        }

      }
    }

    stage('deploy') {
      steps {
        input(message: 'Are you sure to deploy?', ok: 'Yes I\'m sure')
        echo 'Deployment Completed'
      }
    }

    stage('New Build Notification') {
      steps {
        echo 'New Build created successfully'
      }
    }

  }
}