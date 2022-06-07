pipeline{
  agent any
  stages{
    stage("Pull Latest Image"){
      steps{
        bat "docker pull nwatkin3/seleniumdocker"
      }
    }
    stage("Start Grid"){
      steps{
        bat "docker-compose up -d hub chrome firefox"
      }
    }
    stage("Run Test"){
      steps{
        bat "docker-compose up search-module1 search-module2 book-flight-module1 book-flight-module2"
      }
    }
  }
  post{
    always{
      archiveArtifacts artifacts: 'output/**'
      bat "docker-compose down"
    }
  }
}