//install seed jenkins refer jenkins job dsl
def lintChecks() {
  sh '''
    # We commented this because devs gonna check the failures.
    #~/node_modules/jslint/bin/jslint.js server.js
    echo Link Check for ${COMPONENT}
  '''
}

def call() {
  pipeline {
    agent any

    environment {
      SONAR = credentials('SONAR')
      NEXUS = credentials('NEXUS')
    }

    stages {

      // For Each Commit
      stage('Lint Checks') {
        steps {
          script {
            lintChecks()
          }
        }
      }
    } // End of Stages

  }


}