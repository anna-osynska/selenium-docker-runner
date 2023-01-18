pipeline{
   agent any
   stages{
      stage("Start grid"){
         steps{
             sh "docker-compose up -d hub chrome firefox"
         }
      }
      stage("Start test"){
         steps{
             sh "docker-compose up search-module flight-module"
         }
      }
      stage("Grid down"){
         steps{
             sh "docker-compose down"
         }
      }
   }
}