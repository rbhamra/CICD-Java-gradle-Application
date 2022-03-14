pipeline{
    agent any
    stages{
        stage("sonar quality check"){
            agent {
             docker {
                 image 'maven:3.8.4-openjdk-11-slim'
                }   
            }
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonar-token') {
                              sh 'chmod +x gradlew'
                            sh './gradlew sonarqube'
                    }
                   

                }
            }
           
        }
    }
   
}
