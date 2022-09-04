pipeline {
  agent any
  stages {
    stage('Pull Code by web UI') {
      parallel {
        stage('Pull Code by web UI') {
          steps {
            sh 'echo "Pull code by web ui"'
          }
        }

        stage('Pull Code by trigger') {
          steps {
            sh 'echo "Pull code by trigger"'
          }
        }

      }
    }

    stage('Building ') {
      parallel {
        stage('Building ') {
          steps {
            container(name: 'build ', shell: 'echo "build"')
          }
        }

        stage('Scan Code') {
          steps {
            container(name: 'test', shell: 'echo "test"')
          }
        }

      }
    }

    stage('Build Image') {
      steps {
        container(name: 'docker', shell: 'echo "Build Images"')
      }
    }

    stage('Deploy') {
      steps {
        container(name: 'Deploy ', shell: 'echo "Deploy to k8s"')
      }
    }

  }
}