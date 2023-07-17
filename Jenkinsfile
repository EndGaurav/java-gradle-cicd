pipeline{
    agent any
    stages{
        stage("static code analysis"){
            agent {
                docker {
                    images 'openjdk:11'
                }
            }
            steps{
                script {
                    withSonarQubeEnv(credentialsId: 'sonar-token') {
                        sh 'chmod +x gradlew'
                        sh './gradlew sonarqube'
                    }
                }
            }
          
        }
    }
   
}