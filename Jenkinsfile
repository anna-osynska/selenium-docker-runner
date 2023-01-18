pipeline {
   agent any
   stages {
      stage('Start grid') {
         steps {
             bat "docker-compose up -d hub chrome firefox"
         }
      }
      stage('Start test') {
         steps {
             bat "docker-compose up search-module flight-module"
         }
      }
   }
   post {
      always {
        archiveArtifacts artifacts: 'output/**'
        bat "docker-compose down"
      }
   }
}