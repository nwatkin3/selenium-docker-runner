pipeline{
  agent any
  stages{
    stage("Start Grid"){
      steps{
        bat "docker-compose up -d hub chrome firefox"
      }
    }
    stage("Run Test"){
      steps{
        bat "docker-compose up search-module1 search-module2 book-flight-module1 book-flight-module2
      }
    }
    stage("Stop Grid"){
      steps{
        bat "docker-compose down"
      }
    }
  }
}