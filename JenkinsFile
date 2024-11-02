pipeline{
  agent any
  tools{
    maven 'maven'
  }

  stages{
   
    stage("Clean up"){
      steps{
        deleteDir()
      }
    }

    stage("Clone repo"){
      steps{
        sh "git clone https://github.com//hamzamar2019/tp2.git"
      }
    }

    stage("Generate image"){
      steps{
        dir("tp2"){
          sh "mvn clean install"
          sh "docker build -t tp2 ."
        }
      }
    }  

    stage("Run docker compose"){
      steps{
        dir("tp2"){
          sh "docker-compose up -d"
        }
      }
    }
   
   
  }
}
