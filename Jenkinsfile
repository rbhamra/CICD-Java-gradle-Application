pipeline{
    agent{
        any
    }
    stages{
        stage("sonar quality check"){
            agent {
             docker {
                 image 'openjdk:11'
             }   
            }
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonar-token-used-in-jenkins') {
                        sh 'chmod +x gradlew'
                        sh '/gradlew sonarqube'
                    }

                }
            }
           
        }
    }
   
}
