pipeline {
  agent any
  stages {
    stage('Dev') {
      steps {
        echo 'Development'
      }
    }

    stage('Dev Maven Build') {
      steps {
        echo 'Maven build'
      }
    }

    stage('QA Deploy') {
      steps {
        echo 'QA Deploy'
      }
    }

    stage('QA Tests') {
      parallel {
        stage('Web') {
          steps {
            echo 'Web UI'
          }
        }

        stage('API Testing') {
          steps {
            echo 'API Testing'
          }
        }

      }
    }

    stage('QA Certification') {
      steps {
        input 'Approval required for QA'
      }
    }

    stage('UAT deploy') {
      steps {
        echo 'Deployed to UAT'
      }
    }

    stage('UAT certification') {
      steps {
        input 'Approval for UAT cert'
        echo 'UAT cert'
      }
    }

    stage('Prod deploy') {
      steps {
        echo 'Production deployment'
      }
    }

  }
}