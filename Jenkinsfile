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
      stage('Grid down') {
         steps {
             bat "docker-compose down"
         }
      }
   }
}