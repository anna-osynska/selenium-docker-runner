pipeline {
   agent any
   stages {
      stage('Pull image') {
            steps {
                bat "docker pull annasilch/docker3"
            }
      }
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